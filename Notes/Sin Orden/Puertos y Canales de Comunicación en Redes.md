## Propiedades
**Tema General**:
**Etiquetas**: #review #lectura #redes  
**Enlaces**: 

## Esencia Semántica

Un **puerto** en redes es un identificador lógico que permite que múltiples aplicaciones puedan enviar y recibir datos a través de la misma dirección IP sin que los mensajes se mezclen. Existen porque la comunicación en Internet necesita **organizar y separar** los flujos de datos para cada aplicación.

---

## Concepto

Los puertos son **canales virtuales** numerados (del 0 al 65535) que permiten a un dispositivo diferenciar entre los distintos servicios y programas que usan la red.  
Cuando un cliente se conecta a un servidor, se establece una **conexión entre dos direcciones IP y dos puertos** (uno fijo en el servidor y otro dinámico en el cliente).

---

## Puntos Clave

- Un puerto se define con: **IP + Número de puerto**.
    
- Los **puertos fijos** son estándar y reconocidos mundialmente (ej. 80, 443, 25, 3306).
    
- Los **puertos dinámicos** los asigna el sistema operativo cuando una aplicación cliente hace una conexión.
    
- El **servidor** siempre escucha en un puerto fijo conocido, mientras que el **cliente** usa un puerto aleatorio.
    
- La comunicación queda establecida como un **canal exclusivo** entre esos dos extremos.
    

---

## Características

1. **Únicos**: dentro de una misma IP, cada puerto identifica un servicio.
    
2. **Organizados**: se dividen en rangos:
    
    - 0 – 1023: Bien conocidos (HTTP, HTTPS, SMTP).
        
    - 1024 – 49151: Registrados (MySQL, SQL Server, apps de terceros).
        
    - 49152 – 65535: Dinámicos/efímeros (clientes temporales).
        
3. **Bidireccionales**: permiten enviar y recibir datos por el mismo canal.
    
4. **Multiplexados**: varios programas pueden usar la red al mismo tiempo sin confundirse gracias a los puertos.
    
5. **Controlados por el SO**: el sistema operativo gestiona qué aplicación recibe cada paquete según el número de puerto.
    

---

## Analogía

Imagina un **edificio de oficinas**:

- La **dirección IP** es la dirección del edificio.
    
- Los **puertos** son los números de oficina.
    
- El **recepcionista (sistema operativo)** recibe todas las cartas (paquetes de datos) y las entrega en la oficina correcta (aplicación que abrió ese puerto).
    

---

## Ejemplo de Sintaxis (Genérica/Abstracta)