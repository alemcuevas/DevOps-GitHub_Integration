# DevOps-GitHub Integration


## Requisitos Previos

Antes de sumergirte en el código, asegúrate de tener todo en orden:

1. **.NET SDK**: Descarga la última versión desde [aquí](https://dotnet.microsoft.com/download). Este es el motor que impulsa tu aplicación.
2. **Visual Studio Code**: Si no lo tienes, descárgalo [aquí](https://code.visualstudio.com/). Es ligero, poderoso y perfecto para este proyecto.
3. **Extensión de C#**: Desde el marketplace de VS Code, instala esta extensión esencial para trabajar con ASP.NET Core.
4. **Terminal**: Cualquier terminal moderna funciona: Bash, PowerShell o CMD.

---

## Paso 1: Crear un Proyecto Nuevo

1. Abre tu terminal favorita.
2. Ve al directorio donde quieres guardar tu proyecto.
3. Ejecuta este comando para generar tu aplicación:
   
   ```bash
   dotnet new webapp -o UnaAppMas 

  Esto crea la carpeta UnaAppMas con todo lo necesario.

4. Cambia al directorio del proyecto:
  
  ```bash
   cd UnaAppMas
```

## Paso 2: Abrir el Proyecto en Visual Studio Code

1. Lanza Visual Studio Code.
2. Haz clic en **File > Open Folder** y selecciona la carpeta `MiAplicacionWeb`.
3. Si aparece un mensaje, haz clic en "Yes" para agregar configuraciones de depuración.

## Paso 3: Configurar la Extensión de C#

1. Ve al marketplace de Visual Studio Code y asegúrate de que la extensión de **C#** esté instalada.
   - Puedes encontrarla buscando "C#" en la sección de extensiones de VS Code.
2. Una vez instalada, Visual Studio Code generará automáticamente los archivos necesarios para la depuración dentro de la carpeta `.vscode`.
3. Si no se generan automáticamente, reinicia VS Code y abre el proyecto nuevamente para forzar la configuración.

## Paso 4: Ejecutar la Aplicación

1. Abre la terminal integrada en Visual Studio Code. Puedes acceder a ella desde **View > Terminal** o presionando `Ctrl + ```.
2. Ejecuta el siguiente comando para iniciar el servidor de desarrollo:
   ```bash
   dotnet run

## Paso 5: Editar y Personalizar la Aplicación

Ahora que tu aplicación está en funcionamiento, es momento de personalizarla a tu gusto.

1. **Editar la página principal**  
   - Abre el archivo `Pages/Index.cshtml` en Visual Studio Code.
   - Modifica el contenido dentro de las etiquetas `<h1>` para cambiar el mensaje de bienvenida.
   - Guarda los cambios y refresca el navegador para ver la actualización en tiempo real.

2. **Agregar más páginas**  
   - En la carpeta `Pages`, crea un nuevo archivo con la extensión `.cshtml`, por ejemplo: `About.cshtml`.
   - Agrega el siguiente contenido básico:
     ```html
     @page
     <h1>Sobre Nosotros</h1>
     <p>Esta es una nueva página en tu aplicación ASP.NET Core.</p>
     ```
   - Guarda el archivo y prueba acceder a `http://localhost:5000/About`.

3. **Modificar la lógica del backend**  
   - Si necesitas agregar lógica a la página, abre el archivo `Pages/Index.cshtml.cs`.
   - Agrega variables o métodos para manejar datos dinámicos en la vista.

4. **Estilizar la aplicación**  
   - Abre `wwwroot/css/site.css` y personaliza los estilos para cambiar la apariencia de tu aplicación.

🚀 **¡Con estos cambios, tu aplicación empieza a tomar forma!** 


## Laboratorio 1: Creación de un flujo de pull requests automatizado con validaciones.

### Objetivo:

Configurar un flujo de trabajo en GitHub y Azure DevOps que automatice la validación de Pull Requests mediante pruebas y revisiones de código.

## Requisitos Previos

- Repositorio en GitHub con permisos para crear ramas y Pull Requests.
- Cuenta en Azure DevOps con acceso a Pipelines.
- Visual Studio Code con la extensión de GitHub y configurado con tu cuenta.
- .NET SDK instalado y disponible en la terminal.

## Paso 1: Crear una nueva rama para la funcionalidad

1. Abre una terminal en la carpeta del proyecto.
2. Crea una nueva rama con:
   ```bash
   git checkout -b feature/nueva-funcionalidad

3. Realiza cambios en el código y guárdalos.
4. Confirma los cambios:
   ```bash
   git add .
   git commit -m "Agregando nueva funcionalidad"

5. Sube la rama a GitHub:
   ```bash
   git push origin feature/nueva-funcionalidad

## Paso 2: Crear un Pull Request en GitHub

1. Ve a tu repositorio en GitHub.
2. Abre la pestaña Pull Requests y haz clic en New Pull Request.
3. Selecciona la rama feature/nueva-funcionalidad y compárala con main.
4. Agrega un título y descripción significativa.
5. Asigna revisores y etiqueta el PR según sea necesario.
6. Envía el Pull Request para su revisión.

## Paso 3: Configurar validaciones automáticas en Azure DevOps

1. Abre Azure DevOps y navega a la sección Pipelines.
2. Crea un nuevo pipeline y conéctalo con tu repositorio de GitHub.
3. Agrega un archivo YAML para ejecutar pruebas automáticas:
   ```bash
   trigger:
     branches:
       include:
         - main
   pr:
     branches:
       include:
         - feature/*
   pool:
     vmImage: 'ubuntu-latest'
   steps:
   - script: dotnet test
     displayName: 'Ejecutar pruebas unitarias'

4. Guarda y ejecuta el pipeline.
5. Configura reglas de protección de ramas en GitHub para requerir la aprobación del pipeline antes de fusionar cambios.

