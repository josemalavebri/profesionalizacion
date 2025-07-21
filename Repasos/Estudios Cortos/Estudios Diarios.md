
```dataviewjs
function nombreDiaES(date) {
    const dias = ["Domingo", "Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado"];
    return dias[date.getDay()];
}

const hoy = new Date();
hoy.setHours(0, 0, 0, 0);

const ayer = new Date(hoy);
ayer.setDate(ayer.getDate() - 1);

const mañanaDeAyer = new Date(hoy); // inicio de hoy

const archivos = dv.pages()
    .filter(p => {
        if (!p.file || !p.file.ctime) return false;
        let f = p.file.ctime;
        if (!(f instanceof Date)) {
            f = new Date(f);
            if (isNaN(f)) return false;
        }
        return f >= ayer && f < mañanaDeAyer;
    })
    .map(p => {
        let f = p.file.ctime;
        if (!(f instanceof Date)) f = new Date(f);
        return { page: p, fecha: f };
    });

if (archivos.length === 0) {
    dv.paragraph("No se encontraron archivos creados ayer.");
} else {
    const grupos = new Map();

    for (let item of archivos) {
        const fecha = item.fecha;
        // Solo año, mes y día, para agrupar bien
        const diaSolo = new Date(fecha.getFullYear(), fecha.getMonth(), fecha.getDate());
        const key = diaSolo.getTime();
        if (!grupos.has(key)) grupos.set(key, []);
        grupos.get(key).push(item);
    }

    const fechasOrdenadas = Array.from(grupos.keys()).sort((a, b) => a - b);

    for (let ms of fechasOrdenadas) {
        const fecha = new Date(ms);
        const titulo = `${fecha.getDate()} ${nombreDiaES(fecha)}`;
        dv.header(3, titulo);

        const archivosDia = grupos.get(ms)
            .sort((a, b) => a.page.file.ctime - b.page.file.ctime); // orden ascendente por creación

        dv.list(archivosDia.map(a => `[[${a.page.file.name}]]`));
    }
}

```
