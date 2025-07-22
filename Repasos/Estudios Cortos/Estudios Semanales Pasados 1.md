
```dataviewjs
function nombreDiaES(date) {
    const dias = ["Domingo", "Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado"];
    return dias[date.getDay()];
}

// Dado un date, devuelve el lunes y sábado de esa semana
function rangoSemana(date) {
    const diaSemana = date.getDay(); // 0=domingo, 1=lunes, ...
    const lunes = new Date(date);
    lunes.setDate(date.getDate() - (diaSemana === 0 ? 6 : diaSemana - 1)); // si es domingo, retrocede 6 días

    const sabado = new Date(lunes);
    sabado.setDate(lunes.getDate() + 5); // lunes + 5 = sábado

    lunes.setHours(0, 0, 0, 0);
    sabado.setHours(23, 59, 59, 999);
    return { lunes, sabado };
}

const hoy = new Date();
hoy.setHours(0, 0, 0, 0);

const fechaHace1Semana = new Date(hoy);
fechaHace1Semana.setDate(hoy.getDate() - 7);

const { lunes, sabado } = rangoSemana(fechaHace1Semana);

const archivos = dv.pages()
    .filter(p => {
        if (!p.fecha) return false;
        let f = p.fecha;
        if (!(f instanceof Date)) f = new Date(f);
        return f >= lunes && f <= sabado;
    })
    .map(p => {
        let f = p.fecha;
        if (!(f instanceof Date)) f = new Date(f);
        f.setHours(0, 0, 0, 0);
        return { page: p, fecha: f };
    });

if (archivos.length === 0) {
    dv.paragraph(`No se encontraron archivos en la semana del ${lunes.toLocaleDateString('es-ES')} al ${sabado.toLocaleDateString('es-ES')}.`);
} else {
    dv.header(3, `Archivos de la semana del ${lunes.toLocaleDateString('es-ES')} al ${sabado.toLocaleDateString('es-ES')}`);
    const lista = archivos.map(a => `- [[${a.page.file.name}]]`).join('\n');
    dv.paragraph(lista);
}

```









