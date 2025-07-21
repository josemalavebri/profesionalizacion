
```dataviewjs
const folder = "Programacion";

dv.list(
  dv.pages(`"${folder}"`)
    .sort(p => p.file.mtime, 'asc') // Orden ascendente: los últimos al final
    .map(p => dv.fileLink(p.file.path))
);

```

