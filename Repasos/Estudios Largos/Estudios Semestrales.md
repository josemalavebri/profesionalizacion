
```dataviewjs
function nombreDiaES(date) {
    const dias = ["Domingo", "Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado"];
    return dias[date.getDay()];
}

// Último día del mes (para referencia)
function ultimoDiaDelMes(anio, mes) {
    return new Date(anio, mes + 1, 0).getDate();
}

// Dado un date, devuelve el lunes y sábado de esa semana
function rangoSemana(date) {
    const diaSemana = date.getDay(); // 0=domingo, 1=lunes, ...
    const lunes = new Date(date);
    lunes.setDate(date.getDate() - (diaSemana === 0 ? 6 : diaSemana - 1)); // si domingo retrocede 6 días

    const sabado = new Date(lunes);
    sabado.setDate(lunes.getDate() + 5); // lunes + 5 = sábado

    lunes.setHours(0, 0, 0, 0);
    sabado.setHours(23, 59, 59, 999);
    return { lunes, sabado };
}

const hoy = new Date();
hoy.setHours(0, 0, 0, 0);

// Restar 6 meses manteniendo el día ajustado al último válido del mes si es necesario
let anio = hoy.getFullYear();
let mes = hoy.getMonth() - 6;

if (mes < 0) {
    mes += 12;
    anio -= 1;
}

// Ajustar día al último día válido del mes
const diaHoy = hoy.getDate();
const ultimoDia = ultimoDiaDelMes(anio, mes);
const diaAjustado = Math.min(diaHoy, ultimoDia);

const fechaHace6Meses = new Date(anio, mes, diaAjustado);

const { lunes, sabado } = rangoSemana(fechaHace6Meses);

// Filtrar páginas con fecha entre lunes y sábado
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

