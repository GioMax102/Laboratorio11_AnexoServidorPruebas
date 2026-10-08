Ejercicio 0

1. Cada prueba registra a sus personas con un sufijo al azar (ana.f07ea4b1). ¿Qué pasaría si todas usaran ana?
- La segunda prueba fallaría al registrarla (409, ya existe), y la segunda corrida de pytest también. Con el sufijo, cada prueba tiene sus personas y se pueden correr las veces que sea, en cualquier orden.


2. Las pruebas corren contra el PostgreSQL de verdad, no contra una base falsa. ¿Qué se gana? ¿Qué se pierde?
- Se gana que lo que pasa es lo que de verdad hace el servidor: una prueba de permisos contra una base de mentira no demuestra que la real los respete. Se pierde velocidad, y se necesita Docker encendido. Las de la app (Práctica 11) eligieron lo contrario, un servidor de mentira, porque ahí lo que se prueba es la app.