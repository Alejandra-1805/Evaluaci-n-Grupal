
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

<div align="center">
  <table>
    <tr>
      <td><img src="https://github.com/user-attachments/assets/d0db88c2-dd2f-45d9-9761-64f8a1cd3615" width="300"/></td>
      <td><img src="https://github.com/user-attachments/assets/50c99fd1-4e01-404e-979d-ae6d419edef2" width="300"/></td>
    </tr>
  </table>
</div>


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
<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/973f2fb4-a712-4b9c-bae2-5a1005a694ec" width="400"/></td>
    <td><img src="https://github.com/user-attachments/assets/eff6e535-4970-4044-995b-423be9c3469e" width="400"/></td>
    <td><img src="https://github.com/user-attachments/assets/98502371-e60b-4d3f-b32a-f817a3073991" width="400"/></td>
  </tr>
</table>

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

<div align="center"> 
  <table>
    <tr>
      <td><img src="https://github.com/user-attachments/assets/44681c84-d6cb-4c41-9481-269c81085233" width="300"/></td>
      <td><img src="https://github.com/user-attachments/assets/9112f5d8-524f-438a-bd90-066cfae94aa5" width="300"/></td>
    </tr>
  </table>
</div>


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
<div align="center"> 
  <table>
    <tr>
      <td><img src="https://github.com/user-attachments/assets/43bd5ebf-74f4-4717-af98-7e5dc9612bec" width="300"/></td>
      <td><img src="https://github.com/user-attachments/assets/1afa201a-5465-42a0-8b00-ffe7bc64d6de" width="300"/></td>
    </tr>
  </table>
</div>


### 6. Publicación de Sitios Web con GitHub Pages
GitHub Pages permite publicar sitios web estáticos (HTML, CSS y JS) directamente desde un repositorio en GitHub, sin necesidad de hosting adicional.

#### Requisitos
-Tener una cuenta en GitHub

-Tener un repositorio creado (puede estar vacío)

-Un archivo index.html como página de inicio

#### ¿Cómo crear un sitio web con GitHub Pages?
1. Creamos un repositorio
<img src="https://github.com/user-attachments/assets/d29ac85a-a133-4186-a703-1af8120b08d8" width="400" style="border: 1px solid #eee;">
  
2. Creamos un archivo con `.html`.
<img src="https://github.com/user-attachments/assets/6ec33f8d-30b3-497d-9487-a4a6e55cdb0f" width="400" style="border: 1px solid #eee;">

3. Asignamos un nombre y damos click en `Commit changes`
<img src="https://github.com/user-attachments/assets/8e9a7f75-97b5-433a-8428-88de4d5d3344" width="300" style="border: 1px solid #eee;">

4. Ve a <img src="https://github.com/user-attachments/assets/a592fe32-2274-49b0-92be-de7830c4d1d2" width="100" style="border: 1px solid #eee;"> del repositorio, busca la sección de GitHub Pages y selecciona la rama a usar para la publicación.


7. En "settings" nos dirigimos a `pages`
<img src="https://github.com/user-attachments/assets/1a6a7dfe-e518-472c-8e0d-ee5c622fc5ce" width="300" style="border: 1px solid #eee;">


6.En github pages vamos a branch y seleccionamos

<img src="https://github.com/user-attachments/assets/dc4aab3c-728c-4d25-99db-321e19f713b5" width="400" style="border: 1px solid #eee;">


7.Enrutamos el branch para crear la pagina 

<img src="https://github.com/user-attachments/assets/14154079-172c-4334-9dcc-6d2138943ba4" width="400" style="border: 1px solid #eee;">

8.Se genera la pagina : https://nalva19.github.io/pageshit/

<img src="https://github.com/user-attachments/assets/d5e036b7-3d35-4ac4-b694-08eac41fed5f" width="400" style="border: 1px solid #eee;">


##### Ejemplo:
Un simple archivo  `index.html`  puede ser creado como la página de inicio de tu sitio web:

```{html}
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Los Majestuosos Tigres</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f5f5f5;
            color: #333;
        }
        h1 {
            color: #e67e22;
            text-align: center;
            border-bottom: 2px solid #e67e22;
            padding-bottom: 10px;
        }
        .tiger-image {
            width: 100%;
            max-width: 500px;
            height: auto;
            border-radius: 8px;
            margin: 15px auto;
            display: block;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        .section {
            background-color: white;
            padding: 20px;
            margin: 20px 0;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        footer {
            text-align: center;
            margin-top: 30px;
            font-size: 0.9em;
            color: #777;
        }
    </style>
</head>
<body>
    <h1>Los Tigres: Reyes de la Jungla</h1>
    
    <div class="section">
        <h2>El Tigre de Bengala</h2>
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Walking_tiger_female.jpg/800px-Walking_tiger_female.jpg" 
             alt="Tigre de Bengala caminando" 
             class="tiger-image">
        <p>El tigre de Bengala es la subespecie más numerosa, encontrada principalmente en India y Bangladesh. Son conocidos por su pelaje naranja con rayas negras distintivas.</p>
    </div>
    
    <div class="section">
        <h2>El Tigre Siberiano</h2>
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/41/Siberian_tiger_sitting.jpg/800px-Siberian_tiger_sitting.jpg" 
             alt="Tigre Siberiano sentado" 
             class="tiger-image">
        <p>El tigre siberiano es el más grande de todos, adaptado al frío de los bosques rusos. Su pelaje es más grueso y claro que otras subespecies.</p>
    </div>
    
    <div class="section">
        <h2>Datos Curiosos</h2>
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/53/Tiger_water_edit2.jpg/800px-Tiger_water_edit2.jpg" 
             alt="Tigre nadando" 
             class="tiger-image">
        <ul>
            <li>Los tigres pueden nadar hasta 6 km</li>
            <li>Sus rayas son únicas como huellas dactilares</li>
            <li>Un tigre adulto puede comer hasta 40 kg de carne en una noche</li>
        </ul>
    </div>
    
    <footer>
        <p>© 2023 Página Educativa sobre Tigres | Imágenes de Wikimedia Commons</p>
    </footer>
</body>
</html>
</html>
```

### 7. Uso de GitHub Codespaces
#### ¿Qué es GitHub Codespaces?

GitHub Codespaces es un entorno de desarrollo alojado en la nube que permite trabajar desde cualquier lugar, sin necesidad de configurar nada en tu computadora local. Puedes usarlo desde el navegador o desde Visual Studio Code.

---

#### Requisitos previos

- Tener una cuenta activa en [GitHub](https://github.com/).
- Contar con permisos sobre el repositorio donde se desea trabajar.
- Tener instalada la extensión **GitHub Codespaces** en Visual Studio Code (opcional, pero recomendado para trabajar desde el editor local).

---

#### Cómo crear un Codespace

##### Desde GitHub Web:

1. Ingresar al repositorio en GitHub.
  <img src="https://github.com/user-attachments/assets/ff7ec650-dd01-402e-9d24-ee7530c6b6c7" width="400" style="border: 1px solid #eee;">


2. Hacer clic en el botón verde `<> Code`.
 <img src="https://github.com/user-attachments/assets/14547d60-e250-4ba8-9027-c8b00e822d8e" width="400" alt="Captura de pantalla">
 

3. Seleccionar la pestaña **Codespaces**.
  <img src="https://github.com/user-attachments/assets/14547d60-e250-4ba8-9027-c8b00e822d8e" width="400" alt="Captura de pantalla">
  

4. Hacer clic en **+ New codespace**.
5. Esperar a que se cargue el entorno de desarrollo en el navegador.
 <img src="https://github.com/user-attachments/assets/57c8b8d7-7720-4471-af7c-894e6639d40e" width="400" alt="Captura de pantalla">
  
#### Cómo usar Codespaces desde Visual Studio Code

1. Abrir Visual Studio Code.
   
 <img src="https://github.com/user-attachments/assets/d083aee9-e007-43bf-9b0d-1cbedad78e72" width="300" alt="Captura de pantalla">


3. Iniciar sesión en GitHub desde Visual Studio Code.
   
  <img src="https://github.com/user-attachments/assets/39676acb-9831-4837-9d57-f6049bdfb461" width="200" alt="Captura de pantalla">
    
4. Hacer clic en el ícono de **Remote Explorer** o buscar la opción **Codespaces** en la barra lateral izquierda.
   
  <img src="https://github.com/user-attachments/assets/584972ed-c2ec-418d-97a7-6f3346f10b15" width="400" alt="Captura de pantalla">
   
5. Elegir un Codespace existente o crear uno nuevo desde allí.
   
 <img src="https://github.com/user-attachments/assets/84bf9a61-82c4-4400-8a8c-7c30835b58eb" width="400" alt="Captura de pantalla">
  
##### Ejemplo de uso:
Un caso simple como el escribir un comando con extensión de python. 
1. ![Captura de pantalla 2025-05-12 144840](https://github.com/user-attachments/assets/d7bcdfb4-9a0c-4404-8388-e4c853291765)
2.![Captura de pantalla 2025-05-12 150515](https://github.com/user-attachments/assets/ef675b82-472a-4b74-a5ce-568421f49ab7)

3.![Captura de pantalla 2025-05-12 150900](https://github.com/user-attachments/assets/15998425-bf36-475f-aa1f-4c3e1f4312ab)

4. ![Captura de pantalla 2025-05-12 153817](https://github.com/user-attachments/assets/a02c0343-7228-44c5-b0c1-46aada56e760)

### 8. GitHub Dev Editor
El GitHub Dev Editor es una herramienta en línea que permite editar archivos directamente en el navegador sin necesidad de configurar un entorno local.

#### ¿Cómo usar GitHub Dev Editor?
1. Navega a tu repositorio en GitHub.

2. Puedes ingresar directamente https://github.dev/github/dev.

3. Realiza los cambios directamente en la interfaz y guarda tus cambios. Podemos visualizar en https://github.dev/nalva19/dev/tree/patch-1

<!DOCTYPE html>
<html>
<head>
  <title>Mi Web en GitHub</title>
  <link rel="stylesheet" href="estilos.css">
</head>
<body>
  <h1>¡Hola desde GitHub.dev!</h1>
  <button onclick="mostrarMensaje()">Haz clic aquí</button>

  <script src="script.js"></script>
</body>
</html>


## Conclusión

GitHub es una plataforma integral para el control de versiones y la colaboración en proyectos de software. Al dominar las herramientas y flujos de trabajo que ofrece, podrás gestionar proyectos de forma más efectiva, colaborar con otros desarrolladores y automatizar tareas repetitivas. Este manual proporciona una guía completa de las funcionalidades esenciales, y con la práctica, te volverás un experto en el uso de GitHub.

## Referencias

1. [GitHub Documentation](https://docs.github.com/)
2. [GitHub Projects](https://docs.github.com/en/github/managing-your-work-on-github/working-with-projects)
3. [GitHub Actions](https://docs.github.com/en/github/actions)
4. [GitHub Pages](https://docs.github.com/en/github/working-with-github-pages)
5. [GitHub Codespaces](https://docs.github.com/en/github/codespaces)
