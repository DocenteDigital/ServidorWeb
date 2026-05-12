---
title: 03. Imágenes y Contenedores
sidebar_position: 4
description: Domina los dos conceptos técnicos que definen todo el ecosistema de Docker.
---

Si no entiendes la diferencia entre una imagen y un contenedor, estarás perdido cuando empieces a escribir comandos. Vamos a usar una analogía que nunca olvidarás.

##  La Metáfora de la Construcción

Imagina que eres un arquitecto:

1.  **La Imagen es el Plano (Blueprint)**: Es un documento técnico que dice dónde van las paredes, los enchufes y las ventanas. El plano no "existe" físicamente como una casa; no puedes vivir en un papel. Pero el plano contiene **toda la información** necesaria para construir una casa.
2.  **El Contenedor es la Casa**: Es la ejecución física del plano. A partir de **un solo plano**, puedes construir **100 casas idénticas**. Si quemas una casa, el plano sigue intacto. Si quieres cambiar la ventana en todas las casas futuras, cambias el plano.

---

##  ¿Qué es realmente una Imagen?

Técnicamente, una imagen de Docker es un **fichero comprimido** que contiene todo lo necesario para que una aplicación funcione. Lo más fascinante es que se construye por **capas**:

- **Capa 1**: Sistema operativo base (ej: Debian).
- **Capa 2**: El servidor web (ej: Apache).
- **Capa 3**: El lenguaje de programación (ej: PHP 8.2).
- **Capa 4**: Tu código fuente.

Estas capas son **de solo lectura**. Esto hace que las imágenes sean increíblemente ligeras porque si tienes 10 contenedores de PHP, todos comparten las mismas capas base en tu disco duro.

## ¿Qué es un Contenedor?

Es una imagen en ejecución. Cuando lanzas un contenedor, Docker añade una **pequeña capa de escritura** encima de la imagen. 
- Todo lo que creas o borres dentro del contenedor ocurre en esa capa de escritura. 
- **¡Importante!**: Si borras el contenedor, esa capa de escritura desaparece. Por eso decimos que los contenedores son **efímeros**.

##  Docker Hub: La Biblioteca de Planos

¿De dónde sacamos estas imágenes? De [Docker Hub](https://hub.docker.com/). Es como el "GitHub de las imágenes".
- Existen **Imágenes Oficiales**: mantenidas por los creadores del software (PHP, MySQL, Nginx).
- Existen imágenes de la comunidad.

:::danger ¡Ojo con las versiones!
En Docker Hub verás algo llamado **TAGS**. Por ejemplo: `php:8.2-apache`. 
- `php` es el nombre de la imagen.
- `8.2-apache` es el tag (la versión). 
Si no pones tag, Docker bajará por defecto el `latest`, lo cual es una **mala práctica** en entornos profesionales porque puede romper tu código si la versión cambia de repente.
:::
