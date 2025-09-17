# TAREA TRAEFIK

## 1.Verificar requisitos: 
Se verifica que se tenga Docker y Docker-compose 
![Verificar requisitos](img/POST.jpeg)

## 2. Levantar Traefik:
Se levanta el contenedor y se comprueba que el contenedor este activo. 
![Levantar Traefik](https://github.com/julianceron64/TllrInicioTraefik/blob/main/README-MAJO_ESPINOSA/TRAEFICK%202.png?raw=true)

## 3. Acceder al dashboard de Traefik:
Se accedió a el dashboard de traefik mediante el navegador y la URL: http://localhost:8080/dashboard/. 
![dashboard de traefik](img/LOGS-2.png)

## 4.  Desplegar la aplicación de ejemplo
Se levanto el servicio de prueba correctamente
![se desplego la aplicacion de ejemplo](img/LOGS-2.png)


## 5.  Probar acceso a la aplicación: 
Se accedio en el navegador a http://whoami.localhost, y tambien se ejecuto curl http://whoami.localhost. para evidenciar el acceso a la aplicacion.
![Comprobacion acceso a la aplicación](img/LOGS-2.png)


## 5.  Revisar routers en el dashboard:  
Se dirijio a dashboard de Traefik a la sección HTTP Routers y se confirmar que aparece whoami.localhost
![Se revisa routers en el dashboard](img/LOGS-2.png)


## PREGUNTAS
•	¿Qué ventaja aporta enrutar por host (dominio) vs por puerto?

Enrutar por host permite usar el mismo puerto para muchos servicios y diferenciarlos por el nombre del dominio, lo que es más optimo y fácil para el usuario ya que solo entra a direcciones sin preocuparse por puertos. En cambio, enrutar por puerto obliga a usar puertos distintos para cada servicio, lo que lo vuelve difícil de recordar.

•	¿Qué diferencia hay entre labels en los servicios y usar archivos de configuración?

Las labels son reglas que pones directo en el docker-compose.yml, rápidas y fáciles para proyectos pequeños, mientras que los archivos de configuración sirven para manejar reglas más complejas de forma ordenada y separada del código.

•	¿Cómo se entera Traefik de que había servicios nuevos?

Traefik está siempre escuchando a Docker, así que cuando se levanta un contenedor nuevo con labels, lo detecta en automático y agrega la ruta sin que se tenga que reiniciar nada.


