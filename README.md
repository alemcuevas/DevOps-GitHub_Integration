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


