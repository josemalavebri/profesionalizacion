

```dataviewjs
function nombreDiaES(date) {
    const dias = ["Domingo", "Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado"];
    return dias[date.getDay()];
}

function rangoSemana(date) {
    const diaSemana = date.getDay();
    const lunes = new Date(date);
    lunes.setDate(date.getDate() - (diaSemana === 0 ? 6 : diaSemana - 1));
    lunes.setHours(0, 0, 0, 0);

    const sabado = new Date(lunes);
    sabado.setDate(lunes.getDate() + 5);
    sabado.setHours(23, 59, 59, 999);

    return { lunes, sabado };
}

const hoy = new Date();
hoy.setHours(0, 0, 0, 0);

const { lunes, sabado } = rangoSemana(hoy);

const archivos = dv.pages()
    .filter(p => {
        if (!p.file || !p.file.ctime || !p.file.path.startsWith("Notes/")) return false;

        let f = new Date(p.file.ctime);
        if (isNaN(f)) return false;

        // Normalizar la fecha del archivo a las 00:00:00
        f.setHours(0, 0, 0, 0);

        return f >= lunes && f <= sabado;
    })
    .map(p => {
        let f = new Date(p.file.ctime);
        f.setHours(0, 0, 0, 0);
        return { page: p, fecha: f };
    });

if (archivos.length === 0) {
    dv.paragraph(`No se encontraron archivos en la semana del ${lunes.toLocaleDateString('es-ES')} al ${sabado.toLocaleDateString('es-ES')}.`);
} else {
    const grupos = new Map();

    for (let item of archivos) {
        const fecha = item.fecha;
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
            .sort((a, b) => a.page.file.ctime - b.page.file.ctime);

        dv.list(archivosDia.map(a => `[[${a.page.file.name}]]`));
    }
}

```









