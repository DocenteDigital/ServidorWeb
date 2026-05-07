---
title: 01. De XAMPP a Docker
sidebar_position: 2
description: Entiende por qué el desarrollo profesional ha abandonado los entornos monolíticos por los contenedores.
---

Seguramente, hasta hoy, tu flujo de trabajo para PHP ha sido:
1. Abrir **XAMPP Control Panel**.
2. Darle a **Start** en Apache y MySQL.
3. Rezar para que el puerto **80** o el **3306** no estén ocupados por Skype o por otro programa.

Este sistema funciona para aprender las bases de la sintaxis de PHP, pero tiene un **gran problema**: cuando subes tu código al servidor real, las cosas fallan. ¿Por qué? Porque la versión de PHP es distinta, porque falta una extensión instalada, o porque la base de datos se comporta de otra manera.

## 🚀 El Nacimiento de Docker: El Contenedor de Carga

Imagina que quieres enviar una silla, un piano y una televisión de España a Australia. Si los metes sueltos en el barco, llegarán rotos. Pero si los metes en un **Contenedor de Carga estándar**, el barco solo tiene que mover el contenedor. No le importa lo que hay dentro.

**Docker hace lo mismo con el Software.**

Un contenedor de Docker empaqueta:
- Tu código PHP.
- El servidor web (Apache o Nginx).
- Las librerías exactas que necesita tu código.
- La configuración del sistema operativo.

**Todo en una caja aislada del resto del mundo.**

## ⚖️ Comparativa: Virtualización vs. Contenedores

Es común confundir un contenedor con una **Máquina Virtual (VM)** (como las de VirtualBox), pero hay una diferencia de rendimiento abismal:

| Característica | Máquina Virtual (VM) | Contenedor (Docker) |
| :--- | :--- | :--- |
| **Peso** | Gigabytes (instala un SO completo) | Megabytes (solo lo necesario) |
| **Velocidad** | Tarda minutos en arrancar | Arranca en segundos |
| **Rendimiento** | Consume mucha RAM y CPU | Casi no tiene impacto en el host |
| **Aislamiento** | Total (Hardware virtualizado) | Alto (Comparte el Kernel del SO) |

## 🛠️ ¿Por qué Docker es tu nuevo mejor amigo?

1. **Entornos idénticos**: Lo que funciona en tu portátil, funcionará en el servidor de Amazon o Google exactamente igual.
2. **Sin conflictos de versiones**: Puedes tener 10 contenedores con 10 versiones diferentes de PHP funcionando a la vez.
3. **Limpieza absoluta**: Cuando dejas de usar un proyecto, borras el contenedor y tu ordenador queda como si nunca hubieras instalado nada. **¡Se acabó llenar el PC de basura!**

:::info En resumen...
Docker no es solo una herramienta, es un **estándar de la industria**. Aprender esto en 1º de DAW te da una ventaja competitiva enorme respecto a otros desarrolladores.
:::
