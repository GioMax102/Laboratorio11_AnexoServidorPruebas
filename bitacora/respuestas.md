Ejercicio 0

1. Cada prueba registra a sus personas con un sufijo al azar (ana.f07ea4b1). ¿Qué pasaría si todas usaran ana?
- La segunda prueba fallaría al registrarla (409, ya existe), y la segunda corrida de pytest también. Con el sufijo, cada prueba tiene sus personas y se pueden correr las veces que sea, en cualquier orden.


2. Las pruebas corren contra el PostgreSQL de verdad, no contra una base falsa. ¿Qué se gana? ¿Qué se pierde?
- Se gana que lo que pasa es lo que de verdad hace el servidor: una prueba de permisos contra una base de mentira no demuestra que la real los respete. Se pierde velocidad, y se necesita Docker encendido. Las de la app (Práctica 11) eligieron lo contrario, un servidor de mentira, porque ahí lo que se prueba es la app.

Ejercicio B4
Las cuatro pruebas mandan los envíos uno después del otro. ¿Qué parte de crear no ejecuta ninguna? ¿Cómo escribirías una prueba que sí la ejecute?

Ninguna de las ejecuciones son secuenciales dentro de la función de crear. Esta función solo activa dos peticiones con la misma clave de idempotencia, no sucede en una ejecución paralela donde a manera que una se precesa después de la otra. Para ejecutarla así se debe escribir con hilos multithreading, con sus respectivos objetos de sincronización.