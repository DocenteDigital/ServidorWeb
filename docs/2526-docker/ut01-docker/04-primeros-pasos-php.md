---
title: 04. Primeros pasos con PHP
sidebar_position: 5
description: Tutorial práctico para desplegar tu primer servidor web con PHP usando contenedores Docker.
---

¡Es hora de la acción! Vamos a desplegar un servidor web Apache con PHP sin instalar nada más que Docker. Olvida los instaladores pesados; solo necesitamos un comando.

## Preparando nuestro código

Antes de lanzar Docker, crea una carpeta en tu ordenador llamada `mi-web` y, dentro, un archivo `index.php` con este contenido:

```php title="mi-web/index.php"
<?php
  echo "<h1>¡Hola desde mi contenedor de Docker!</h1>";
  echo "<p>PHP está funcionando correctamente.</p>";
  phpinfo();
?>
```

##  Lanzando el Contenedor

Abre tu terminal dentro de esa carpeta y ejecuta el siguiente comando (léelo con calma, ahora lo explicamos):

```bash title="Comando en Terminal"
docker run -d -p 8080:80 --name mi-servidor -v ${PWD}:/var/www/html php:8.2-apache
```

### ¿Qué significa cada parte?
- **`docker run`**: "Crea y arranca un contenedor".
- **`-d`** (Detached): Corre en segundo plano. Así puedes seguir usando la terminal.
- **`-p 8080:80`**: Mapeo de puertos. El puerto **8080** de tu PC se conecta al puerto **80** (HTTP) del contenedor.
- **`--name mi-servidor`**: Le damos un nombre amigable para no tener que usar el ID raro que genera Docker.
- **`-v ${PWD}:/var/www/html`**: Esto es magia. Conecta tu carpeta actual (`PWD`) con la carpeta donde Apache busca la web dentro del contenedor. **Si cambias el código en VS Code, se verá el cambio al instante.**
- **`php:8.2-apache`**: La imagen (el plano) que vamos a usar.

---

##  Verificación

Abre tu navegador y entra en `http://localhost:8080`. Si ves el mensaje y la tabla de `phpinfo()`, ¡estás ejecutando PHP dentro de un contenedor!

##  Comandos de Supervivencia

Aquí tienes el "kit de emergencia" para gestionar tus contenedores:

- **Listar contenedores activos**: `docker ps`
- **Listar todos (incluso parados)**: `docker ps -a`
- **Detener el servidor**: `docker stop mi-servidor`
- **Arrancarlo de nuevo**: `docker start mi-servidor`
- **Eliminarlo**: `docker rm -f mi-servidor` (El `-f` fuerza el borrado aunque esté encendido).

:::tip Tip de Profesional
Si quieres entrar "dentro" del contenedor para ver los archivos como si fuera una terminal de Linux, usa:
`docker exec -it mi-servidor bash`
:::
