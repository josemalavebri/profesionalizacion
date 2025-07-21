
```dataviewjs
const pages = dv.pages('"Programacion"').where(p => p.file.tags);
let grupos = {};
let unitarias = new Set();
let grupoLSL = {};

// Clasificar las etiquetas
for (let page of pages) {
    for (let tag of page.file.tags) {
        let limpio = tag.replace(/^#/, "");
        let partes = limpio.split("-");

        if (partes.length > 1) {
            let tipo = partes[0];

            if (tipo === "lsl" && partes[1] === "asdf") {
                if (!grupoLSL[tipo + "-" + partes[1]]) grupoLSL[tipo + "-" + partes[1]] = new Set();
                grupoLSL[tipo + "-" + partes[1]].add(tag);
            } else {
                if (!grupos[tipo]) grupos[tipo] = new Set();
                grupos[tipo].add(tag);
            }
        } else {
            unitarias.add(tag); // etiquetas sin "-"
        }
    }
}

// Mostrar grupo #lsl-asdf
if (Object.keys(grupoLSL).length > 0) {
    dv.header(2, "#lsl-asdf");
    for (let subgrupo of Object.keys(grupoLSL).sort()) {
        dv.header(4, subgrupo);
        let lista = Array.from(grupoLSL[subgrupo]).sort();
        dv.list(lista);
    }
}

// Mostrar etiquetas unitarias
if (unitarias.size > 0) {
    dv.header(3, "Etiquetas unitarias");
    const listaUnitarias = Array.from(unitarias).sort();
    dv.list(listaUnitarias);
}

// Mostrar el resto de grupos
for (let tipo of Object.keys(grupos).sort()) {
    dv.header(4, tipo);
    let lista = Array.from(grupos[tipo]).sort();
    dv.list(lista);
}

```

