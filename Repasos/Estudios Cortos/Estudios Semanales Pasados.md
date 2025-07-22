
```dataviewjs
// Función para obtener el nombre del día en español
function nombreDiaES(date) {
    const dias = ["Domingo", "Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado"];
    return dias[date.getDay()];
}

// Dado un date, devuelve el lunes y sábado de esa semana
function rangoSemana(date) {
    const diaSemana = date.getDay();
    const lunes = new Date(date);
    lunes.setDate(date.getDate() - (diaSemana === 0 ? 6 : diaSemana - 1));
    const sabado = new Date(lunes);
    sabado.setDate(lunes.getDate() + 5);
    lunes.setHours(0, 0, 0, 0);
    sabado.setHours(23, 59, 59, 999);
    return { lunes, sabado };
}

// Obtener lunes y sábado de hace 2 semanas
const hoy = new Date();
hoy.setHours(0, 0, 0, 0);
const fechaHace2Semanas = new Date(hoy);
fechaHace2Semanas.setDate(hoy.getDate() - 14);
const { lunes, sabado } = rangoSemana(fechaHace2Semanas);

// Filtrar archivos entre el lunes y sábado de esa semana
const archivos = dv.pages()
    .filter(p => {
        if (!p.fecha) return false;
        let f = p.fecha instanceof Date ? p.fecha : new Date(p.fecha);
        return f >= lunes && f <= sabado;
    })
    .map(p => {
        let f = p.fecha instanceof Date ? p.fecha : new Date(p.fecha);
        f.setHours(0, 0, 0, 0);
        return { page: p, fecha: f };
    });

// Mostrar resultados
if (archivos.length === 0) {
    dv.paragraph(`No se encontraron archivos en la semana del ${lunes.toLocaleDateString('es-ES')} al ${sabado.toLocaleDateString('es-ES')}.`);
} else {
    dv.header(3, `Archivos de la semana del ${lunes.toLocaleDateString('es-ES')} al ${sabado.toLocaleDateString('es-ES')}`);
    const lista = archivos.map(a => `- [[${a.page.file.name}]]`).join('\n');
    dv.paragraph(lista);
}

```









