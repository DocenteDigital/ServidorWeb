---
title: UT1. Introducción a Docker
sidebar_position: 1
description: Guía completa de inicio a Docker para alumnos de DAW. De XAMPP a la profesionalización con contenedores.
---

¡Bienvenido a la **Unidad de Trabajo 1**! Si estás aquí, es porque estás a punto de dar el salto de "hacer páginas web" a **gestionar entornos de servidores profesionales**. 

Hasta ahora, probablemente hayas usado herramientas como **XAMPP o WAMP**. Son geniales para empezar, pero en el mundo real, los servidores no se gestionan instalando un `.exe` y dando a un botón de "Start". Se gestionan mediante **Contenedores**.

##  Objetivos de esta Unidad

Al finalizar esta unidad, serás capaz de:
- **Comprender** la diferencia real entre la virtualización tradicional y la de contenedores.
- **Instalar y configurar** un entorno de desarrollo profesional en Windows usando **WSL 2**.
- **Dominar** los comandos esenciales de Docker para desplegar servicios en segundos.
- **Orquestar** un entorno completo de **PHP y MySQL** que sea idéntico al que usarás en producción.
- **Solucionar** el mítico problema de: *"¡Pero si en mi ordenador funcionaba!"*.

## Mapa de la Unidad

Para que no te pierdas, hemos dividido el aprendizaje en bloques lógicos:

1.  **[El Cambio de Paradigma](./01-de-xampp-a-docker.md)**: ¿Por qué Docker ha matado a XAMPP en las empresas?
2.  **[Preparando los Cimientos](./02-instalacion-y-configuracion.md)**: Instalación crítica de WSL 2 y Docker Desktop.
3.  **[Anatomía de Docker](./03-imagenes-y-contenedores.md)**: Diferenciando entre la "receta" (imagen) y el "plato" (contenedor).
4.  **[Manos a la Obra con PHP](./04-primeros-pasos-php.md)**: Tu primer servidor web "dockerizado".
5.  **[Datos y Redes](./05-persistencia-y-redes.md)**: Cómo hacer que tus bases de datos sobrevivan y tus servicios se hablen entre sí.
6.  **[El Combo Profesional: Docker Compose](./06-entorno-servidores-compose.md)**: Levantando todo tu stack tecnológico con un solo comando.

:::tip ¿Por qué Docker ahora?
En el módulo de **Entorno Servidor**, vamos a trabajar con diferentes versiones de bases de datos y lenguajes. Docker te permite tener **PHP 8.2** para un proyecto y **PHP 7.4** para otro en el mismo ordenador sin que se peleen entre ellos. ¡Es magia negra para la productividad!
:::
