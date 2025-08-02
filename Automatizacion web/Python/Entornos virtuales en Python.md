---
sr-due: 2025-08-06
sr-interval: 5
sr-ease: 230
---

#tipo-documento #review  
## Esencia semántica
+ Los entornos virtuales en Python 
	+ son espacios aislados donde
		+ se instalan las dependencias y el intérprete específico de un proyecto, sin afectar el Python global del sistema ni otros proyectos.
	+  Permiten evitar 
		+ conflictos de versiones y asegurar que cada proyecto funcione 
			+ con las librerías exactas que necesita.

+ Un entorno virtual en Python es una 
	+ copia ligera e independiente del intérprete Python, junto con su propia carpeta para librerías 
		+ (`site-packages`). 
	+ Esto crea un 
		+ espacio aislado donde se instalan las dependencias exclusivamente para un proyecto.

> El entorno virtual se activa para que la consola o el proceso utilice ese intérprete local y sus librerías, no el global del sistema.
## Puntos clave
- Python instala 
	- un intérprete global accesible para todo el sistema.
- Sin entornos virtuales, 
	- todas las librerías instaladas con `pip` se comparten globalmente.
- Los entornos virtuales replican el intérprete y crean 
	- un espacio local de librerías para cada proyecto.
- Esto permite evitar
	-  conflictos de versiones entre proyectos.
- Se activan manualmente para 
	- “cambiar” el intérprete y el contexto de librerías.
- Facilitan la reproducibilidad del entorno (por ejemplo, usando `requirements.txt`).
- Son especialmente útiles 
	- cuando se trabaja con varios proyectos en una misma máquina.

## Características

|                         |                                             |
| ----------------------- | ------------------------------------------- |
| Aislamiento             | Intérprete y librerías propios por proyecto |
| Activación              | Manual, para cambiar el contexto al entorno |
| Instalación de paquetes | Solo dentro del entorno virtual             |
| Ubicación               | Carpeta del entorno, p.ej. `.venv/`         |
| Impacto en sistema      | No afecta el Python ni librerías globales   |
| Compatibilidad          | Compatible con cualquier versión de Python  |
|                         |                                             |

## Analogía

> *Piensa en el intérprete Python global como un motor instalado en tu garaje (computadora) que todos los carros (proyectos) usan. Si modificas ese motor, afecta a todos los carros. Crear un entorno virtual es como construir un mini garaje para cada carro, con su propio motor independiente, para que las modificaciones solo afecten a ese carro y no al resto.*
## Ejemplos
### Sintaxis 
```json
# Crear un entorno virtual en la carpeta .venv
python -m venv .venv

# Activar el entorno virtual
# Windows
.\.venv\Scripts\activate
# Linux/macOS
source .venv/bin/activate

# Instalar una librería solo en el entorno
pip install requests

# Guardar las dependencias instaladas
pip freeze > requirements.txt

# Instalar dependencias de un proyecto con requirements.txt
pip install -r requirements.txt


```


[[Comparación del manejo de dependencias entre Python (entornos virtuales), Angular y .NET]]
