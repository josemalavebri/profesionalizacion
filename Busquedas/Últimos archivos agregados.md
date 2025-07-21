
```dataviewjs
const folder = "Programacion";
const hoy = new Date();
const haceUnMes = new Date();
haceUnMes.setMonth(hoy.getMonth() - 1);

let archivos = dv.pages(`"${folder}"`)
  .where(p => p.file.ctime >= haceUnMes)
  .sort(p => p.file.ctime, 'desc');

dv.table(
  ["Archivo", "Fecha de creación"],
  archivos.map(p => [
    p.file.link,
    p.file.ctime.toLocaleString()
  ])
);

```

