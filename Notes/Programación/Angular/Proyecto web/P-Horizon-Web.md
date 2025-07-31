
## 1. Estructura General del Proyecto

El proyecto está organizado en una arquitectura modular, típica de Angular, con una carpeta principal ([core](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)) que contiene componentes reutilizables, servicios, directivas, interfaces, middlewares, pipes y utilidades. Además, hay un subproyecto Angular en [horizon-academic](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) que contiene la aplicación principal.
## 2. Temario Sugerido para Estudio
### A. Fundamentos y Configuración

1. Revisar [README.md](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) y [package.json](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) para entender dependencias y scripts principales. 2. Analizar [angular.json](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) y [tsconfig.json](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) para comprender la configuración global del proyecto.

### B. Core del Proyecto

3. Componentes reutilizables: [components](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)  - Ejemplo: `fade-effect`, `loader`, `typing-effect` 4. Directivas personalizadas: [directives](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)  - Ejemplo: `back-button`, `solo-letras`, `solo-mayusculas`, `solo-numeros` 5. Pipes personalizados: [pipes](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)  - Ejemplo: `fecha-legible`, `format-date`, `safe-number` 6. Servicios: [services](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)  - Autenticación, navegación, carga, usuarios, etc. 7. Middlewares/interceptores: [middlewares](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)  - Ejemplo: `auth-token.interceptor.ts`, `url-patcher.interceptor.ts` 8. Utilidades y constantes: [utils](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html), [constans](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)

### C. Dominio y Lógica de Negocio

9. Interfaces y modelos: [interfaces](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)  - Define la estructura de datos y contratos. 10. Enrutadores y guards: [guards](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)  - Control de acceso y navegación.

### D. Aplicación Principal

11. Entrar a [app](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)  - Analizar los módulos principales, como `dashboard`, `admin`, `alumnos`, etc. 12. Flujo de registro y gestión de alumnos: `dashboard/admin/alumnos/registrar-alumnos/`  - Entender cómo se crean, editan y gestionan los alumnos.

### E. Configuración Avanzada

13. Tailwind y estilos: [tailwind.config.ts](vscode-file://vscode-app/c:/Users/josem/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) 14. Internacionalización, temas y configuración adicional.

### F. Pruebas y Mantenimiento

15. Revisar archivos `.spec.ts` para entender la estrategia de testing. 16. Scripts de mantenimiento y utilidades.

---

## Recomendación de Estudio

- Empieza por la configuración general y la estructura de carpetas.
- Luego estudia los componentes y servicios del core.
- Después, revisa la lógica de negocio y los flujos principales de la app.
- Finalmente, explora las pruebas y configuraciones avanzadas.

¿Te gustaría que te detalle el flujo de algún módulo o funcionalidad específica?