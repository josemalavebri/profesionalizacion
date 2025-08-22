---
sr-due: 2025-08-27
sr-interval: 14
sr-ease: 150
---

#review 
## Ver más allá del código: Preguntarse el "¿por qué?"
+ Un desarrollador junior ve una PR como una tarea cumplida. Un senior analiza si esa es **la mejor solución posible**:
	- ¿Por qué se eligió esa lógica?
	- ¿Hay alternativas más eficientes?
	- ¿Estamos trayendo más datos de los necesarios?
	- ¿Qué pasaría con este código si hay millones de registros
### Ejemplo:
+ Si una función exporta usuarios _premium_, pero se hace un `getAllUsers()` de toda la base de datos… ¿no sería mejor filtrar en la consulta y solo obtener los necesarios?  
>  El _senior_ debe pensar en **eficiencia**, **memoria**, **performance** y uso real del sistema en producción
---

## Detectar bombas de relojería en el código
Hay partes del código que no parecen problemáticas **ahora**, pero que en el futuro pueden romper el sistema.
### Señales de alarma comunes:
- Comparaciones con valores "mágicos" (ej: `nivel > 5`)
- Lógica de negocio metida en condicionales simples
- Dependencia de decisiones estáticas de diseño

**Solución:** Abstraer la lógica a métodos como `esPremium()` o delegar a servicios que representen la lógica de negocio. Así evitas que un cambio de requisitos (como que `nivel 7` ya no sea premium) rompa todo el sistema.

> Comenta las PR preguntando si el código está **preparado para cambios futuros**.
---
## Tener una vista arquitectónica y mantener la coherencia del proyecto
Un código que funciona no siempre es un buen código. El objetivo es que además sea **coherente con la arquitectura general del proyecto**.
### **Malas prácticas comunes:**
- Usar llamadas directas a base de datos (`getAllUsersFromDB()`) en lugar de utilizar el patrón **Repositorio**
- Reimplementar lógica ya existente (como enviar correos) sin reutilizar los componentes comunes
- Clases que hacen demasiadas cosas al mismo tiempo (crear CSV, mandar email, procesar datos…

---
## Tareas para mejorar la lógica al inspeccionar un Pr
- **Pregunta el "por qué"**: 
	- ¿Es esta la mejor solución? ¿Qué otras opciones hay?
- **Busca las bombas de relojería**: 
	- ¿Qué pasaría si algo cambia?
- **Ten visión arquitectónica**: 
	- ¿Este código respeta la arquitectura global?