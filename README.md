# TllrInicioTraefik

En la siguiente imagen podemos ver como se levanto el contenedor de traefik para la prueba 
![Texto alternativo](https://github.com/julianceron64/TllrInicioTraefik/blob/main/1.jpg?raw=true)

En las siguientes dos imagenes se puede ver que se levanto un servicio de prueba con un whoami.yml y su correspondiente comprobación con una petición curl
![Texto alternativo](https://github.com/julianceron64/TllrInicioTraefik/blob/main/2.jpg?raw=true)
![Texto alternativo](https://github.com/julianceron64/TllrInicioTraefik/blob/main/3.jpg?raw=true)

En la última imagen podemos ver la comprobación directa en el dashboard de Traefik accediendo a localhost:8080/dashboard/. Allí se observa que los entrypoints, routers y services están activos, lo que confirma que el proxy inverso está funcionando de forma correcta y detectando automáticamente los servicios configurados:

![Texto alternativo](https://github.com/julianceron64/TllrInicioTraefik/blob/main/4.jpg?raw=true)

# Respuestas a las preguntas

1. ¿Qué ventaja aporta enrutar por host (dominio) vs por puerto?

Enrutar por dominio permite tener varios servicios en el mismo puerto diferenciándolos por el nombre del host, lo que facilita la gestión de certificados y es más ordenado en producción, mientras que enrutar por puerto obliga a usar un puerto distinto para cada servicio, lo cual complica la escalabilidad.

2. ¿Qué diferencia hay entre labels en los servicios y usar archivos de configuración?

Los labels permiten definir la configuración directamente en los contenedores y traefik las detecta automáticamente, lo que las hace prácticas para entornos dinámicos, mientras que los archivos de configuración son más estáticos pero ofrecen un mayor control y organización, siendo útiles en proyectos grandes o cuando no se usa Docker.

3. ¿Cómo se entera Traefik de que había servicios nuevos?

En Docker, traefik se entera de los nuevos servicios porque se conecta directamente a la API del motor de docker. Cada vez que se levanta un contenedor con las labels correspondientes, traefik lo detecta automáticamente y crea la ruta hacia ese servicio; de la misma forma, cuando el contenedor se detiene, traefik lo elimina de su configuración sin necesidad de reiniciar nada.
