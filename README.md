
# Manual de Uso de GitHub

## Introducción

GitHub es una de las plataformas más populares para el control de versiones y colaboración en proyectos de desarrollo de software. Este manual tiene como objetivo proporcionar una guía completa para usar GitHub, cubriendo sus funcionalidades clave, desde la creación de repositorios hasta la automatización de flujos de trabajo, publicación de sitios web, y más. Al aprender estas herramientas, podrás mejorar la eficiencia de tu equipo y gestionar proyectos de forma más eficaz.

### 1. Issues

Los **Issues** son una de las características más útiles de GitHub para gestionar tareas, errores y mejoras en un proyecto. Pueden ser utilizados para discutir problemas, planificar tareas y asignar responsabilidades.

#### ¿Cómo crear un Issue?

Para crear un **Issue**:

1. Dirígete a la pestaña "Issues" de tu repositorio.
2. Haz clic en el botón "New Issue".
3. Escribe un **título** claro y una **descripción** detallada. Aquí puedes indicar si es un error, una nueva funcionalidad, una tarea o una pregunta.
4. Si es necesario, puedes asignar etiquetas y asignar el Issue a un miembro del equipo.

| PASO 1 | PASO 2 |
|----------|----------|
| ![Image 1](https://github.com/user-attachments/assets/d0db88c2-dd2f-45d9-9761-64f8a1cd3615) | ![Image 2](https://github.com/user-attachments/assets/50c99fd1-4e01-404e-979d-ae6d419edef2) |

##### Ejemplo:

- **Título**: Error al hacer login
- **Descripción**: Al intentar hacer login en la aplicación, el sistema muestra un mensaje de "Credenciales incorrectas" incluso cuando los datos son correctos.

Este Issue puede ser asignado al desarrollador encargado del **backend**.

> **Backend**: El **backend** es la parte del sistema que no se ve. Es el "motor" que está detrás de la aplicación, encargándose de la gestión de datos, la lógica de negocio y el almacenamiento. Se comunica con el **frontend** (la parte visible de la aplicación) para mostrar la información adecuada.


```{r pressure, echo=FALSE}
#plot(pressure)
```

### 2. Pull Request

Un **Pull Request (PR)** es una solicitud para que los cambios realizados en una rama se integren con la rama principal del repositorio. Los Pull Requests permiten la revisión del código antes de su fusión.

#### ¿Cómo crear un Pull Request?

1. Primero, crea una rama para trabajar en una nueva característica o corrección de error.
2. Realiza tus cambios y haz commit en tu rama.
3. Dirígete a la pestaña "Pull Requests" y haz clic en "New Pull Request".
4. Elige las ramas de comparación (la rama donde hiciste los cambios) y la base (usualmente `main` o `master`).
5. Añade un **título** y una **descripción** detallada de los cambios realizados. Explica por qué estos cambios son necesarios.
6. Haz clic en "Create Pull Request" para enviarlo.

##### Ejemplo de mensaje para un Pull Request:

- **Título**: Añadir validación al formulario de login
- **Descripción**: Este Pull Request agrega una validación para asegurarse de que el campo del correo electrónico no esté vacío antes de enviar el formulario. También se ha corregido un error en la validación de la contraseña.

Este Pull Request es revisado por otros miembros del equipo antes de ser fusionado con la rama principal.

### 3. Gestión de Proyectos con GitHub Projects

**GitHub Projects** permite organizar tareas de un proyecto mediante tableros de estilo Kanban. Puedes crear columnas personalizadas y agregar tarjetas que representen tareas.

#### ¿Cómo usar GitHub Projects?

1. Dirígete a la pestaña "Projects" de tu repositorio.
2. Haz clic en "New Project" para crear un nuevo tablero.
3. Crea columnas como "To Do", "In Progress" y "Done", y agrega tareas como tarjetas dentro de cada columna.
4. Asigna tareas a miembros del equipo y establece fechas límite.

##### Ejemplo de tablero de Kanban:

- **Columna "To Do"**: Crear el formulario de login.
- **Columna "In Progress"**: Desarrollar la funcionalidad de validación.
- **Columna "Done"**: Integración del formulario con la base de datos.

GitHub Projects ayuda a visualizar el progreso del proyecto y facilita la organización del trabajo en equipo.

### 4. Automatización de Flujos de Trabajo con GitHub Actions

**GitHub Actions** permite automatizar tareas como pruebas, despliegues y otros flujos de trabajo relacionados con el ciclo de vida del software. Puedes definir flujos de trabajo mediante archivos YAML.

#### ¿Cómo configurar un flujo de trabajo con GitHub Actions?

1. Ve a la pestaña "Actions" de tu repositorio.
2. Selecciona un flujo de trabajo existente o crea uno nuevo haciendo clic en "New Workflow".
3. Elige un archivo de plantilla o escribe un archivo YAML para definir los pasos a automatizar.

##### Ejemplo de flujo de trabajo para pruebas automatizadas:

```{yaml}
name: Node.js CI

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2
      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '14'
      - name: Install dependencies
        run: npm install
      - name: Run tests
        run: npm test
```

Este flujo de trabajo ejecutará las pruebas automáticamente cada vez que haya un push en la rama `main`.

> **Push**: **Push** es el comando que se usa para subir los cambios locales a un repositorio remoto, como GitHub. Es un paso importante para compartir tu trabajo con otros colaboradores.

### 5. Uso de GitHub Gits
**Git** es el sistema de control de versiones utilizado por GitHub. Permite gestionar los cambios en los archivos a lo largo del tiempo y facilita la colaboración entre los desarrolladores.

#### Comandos básicos de Git:
`git clone`: Clona un repositorio en tu máquina local.

`git add`: Añade archivos al área de preparación (staging area).

`git commit`: Realiza un commit con los cambios preparados.

`git push`: Sube los cambios locales al repositorio remoto.

##### Ejemplo de flujo básico con Git:

```{yaml}
git clone https://github.com/usuario/repositorio.git
cd repositorio
git checkout -b nueva-rama
# Realizas cambios en los archivos
git add .
git commit -m "Agregando nueva funcionalidad"
git push origin nueva-rama
```

### 6. Publicación de Sitios Web con GitHub Pages
GitHub Pages permite crear y publicar sitios web estáticos directamente desde un repositorio. Es útil para blogs, portfolios y documentación.

#### ¿Cómo crear un sitio web con GitHub Pages?
1. Crea una nueva rama llamada `gh-pages` o usa la rama principal.

2. Sube tus archivos HTML, CSS y JS al repositorio en esta rama.

3. Ve a "Settings" del repositorio, busca la sección de GitHub Pages y selecciona la rama a usar para la publicación.

##### Ejemplo:
Un simple archivo `index.html` puede ser creado como la página de inicio de tu sitio web:

```{html}
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Proyecto</title>
</head>
<body>
    <h1>Bienvenidos a mi sitio web en GitHub Pages</h1>
    <p>Este es un ejemplo de cómo publicar sitios web estáticos en GitHub.</p>
</body>
</html>
```

### 7. Uso de GitHub Codespaces
GitHub Codespaces proporciona un entorno de desarrollo integrado (IDE) en la nube, lo que permite desarrollar sin tener que configurar tu entorno local.

#### ¿Cómo usar GitHub Codespaces?
1. Abre tu repositorio en GitHub.

2. Haz clic en el botón "Code" y luego selecciona "Open with Codespaces".

3. Esto abrirá el entorno de desarrollo directamente en tu navegador, listo para programar.

##### Ejemplo de uso:
Si estás trabajando en un proyecto `Node.js`, puedes abrir GitHub Codespaces y comenzar a editar los archivos, ejecutar pruebas y hacer commits directamente desde la interfaz web.

### 8. GitHub Dev Editor
El GitHub Dev Editor es una herramienta en línea que permite editar archivos directamente en el navegador sin necesidad de configurar un entorno local.

#### ¿Cómo usar GitHub Dev Editor?
1. Navega a tu repositorio en GitHub.

2. Haz clic en el botón de editar (pencil) en cualquier archivo para abrir el editor.

3. Realiza los cambios directamente en la interfaz y guarda tus cambios.

## Conclusión

GitHub es una plataforma integral para el control de versiones y la colaboración en proyectos de software. Al dominar las herramientas y flujos de trabajo que ofrece, podrás gestionar proyectos de forma más efectiva, colaborar con otros desarrolladores y automatizar tareas repetitivas. Este manual proporciona una guía completa de las funcionalidades esenciales, y con la práctica, te volverás un experto en el uso de GitHub.

## Referencias

1. [GitHub Documentation](https://docs.github.com/)
2. [GitHub Projects](https://docs.github.com/en/github/managing-your-work-on-github/working-with-projects)
3. [GitHub Actions](https://docs.github.com/en/github/actions)
4. [GitHub Pages](https://docs.github.com/en/github/working-with-github-pages)
5. [GitHub Codespaces](https://docs.github.com/en/github/codespaces)
