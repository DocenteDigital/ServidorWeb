---
title: 02. Instalación y Configuración
sidebar_position: 3
description: Paso a paso para configurar tu entorno Windows con WSL 2 y Docker Desktop.
---

Instalar Docker en Windows solía ser un dolor de cabeza. Hoy, gracias a **WSL 2 (Windows Subsystem for Linux)**, es una experiencia fluida y profesional.

##  El Cimiento: WSL 2 (Windows Subsystem for Linux)

Docker no corre nativamente sobre el núcleo (kernel) de Windows. Necesita Linux. WSL 2 permite que Windows ejecute un núcleo de Linux real dentro de tu sistema sin ralentizarlo.

### Paso 1: Verificación de WSL
Antes de nada, comprueba si ya lo tienes instalado. Abre un **PowerShell** y escribe:

```bash title="Comando en Terminal"
wsl --version
```

- **Si ves un número de versión**: ¡Felicidades! Puedes saltar al siguiente paso.
- **Si recibes un error**: Debes instalarlo.

### Paso 2: Instalación de WSL (Si no lo tienes)
Ejecuta este comando en **PowerShell como Administrador**:

```bash title="Instalación de WSL"
wsl --install
```

> [!WARNING] Reinicio Obligatorio
> Tras ejecutar este comando, **debes reiniciar tu ordenador**. Sin el reinicio, los cambios en el kernel no se aplicarán y Docker fallará.

---

## 🐳 Instalando Docker Desktop

Una vez que Windows tiene "corazón de Linux" (WSL 2), instalamos la interfaz que gestionará todo.

1.  **Descarga**: Ve a la web oficial de [Docker Desktop](https://www.docker.com/products/docker-desktop/) y descarga el instalador para Windows.
2.  **Instalación**: Ejecuta el `.exe`. Asegúrate de que la casilla **"Use WSL 2 instead of Hyper-V"** esté marcada.
3.  **Primer Inicio**: Al abrir Docker Desktop, acepta los términos y espera a que el icono de la ballena en la barra de tareas se quede quieto (en verde).

## 🔍 Verificación Final

Para estar 100% seguros de que todo está OK, abre una terminal (la que quieras: PowerShell, CMD o la terminal de VS Code) y lanza:

```bash title="Comando de Verificación"
docker --version
docker run hello-world
```

### ¿Qué acaba de pasar?
Si ves un mensaje que dice **"Hello from Docker!"**, significa que:
1. Tu terminal ha hablado con el motor de Docker.
2. Docker ha ido a internet (Docker Hub) a buscar una imagen llamada `hello-world`.
3. Ha creado un contenedor a partir de esa imagen.
4. Ha ejecutado el código de dentro y te ha mostrado el resultado.

:::tip ¿Problemas con la Virtualización?
Si Docker te da un error tipo "Hardware assisted virtualization must be enabled in the BIOS", significa que debes entrar en la BIOS de tu PC y activar la opción **VT-x** (Intel) o **AMD-V**. ¡Es un paso común en muchos portátiles!
:::
