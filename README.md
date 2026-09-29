# EntradasMvc — práctica guiada MVC

Proyecto base de ASP.NET Core MVC con C#, .NET 10, sin autenticación, con HTTPS y sin contenedores, creado directamente en esta carpeta para Visual Studio Code.

Se implementó el código de la práctica: `Models/Cotizacion.cs`, `Controllers/EntradasController.cs`, `Views/Entradas/Index.cshtml`, `Views/Entradas/Resultado.cshtml` y el enlace **Cotizar entradas** en el menú. Se conserva la plantilla original, incluidas las páginas Home y Privacy y `Program.cs`, con `AddControllersWithViews()` y la ruta `{controller=Home}/{action=Index}/{id?}`.

El formulario valida un nombre de 3 a 60 caracteres y una cantidad de 1 a 10 entradas. Cada entrada cuesta Bs 50 y desde 5 entradas se aplica un descuento del 10 %. Las preguntas de la práctica quedan pendientes.

## Abrir y ejecutar en Visual Studio Code

1. Usa **Archivo → Abrir carpeta…** y selecciona esta carpeta `MVC`.
2. C# Dev Kit y SQLite Viewer ya están instalados en este equipo. También figuran como extensiones recomendadas del proyecto.
3. Pulsa **F5** y selecciona **EntradasMvc (HTTPS)** para ejecutar y depurar, o ejecuta en la terminal integrada:

```sh
dotnet run --launch-profile https
```

Abre <https://localhost:7180> y pulsa **Cotizar entradas**, o entra directamente en <https://localhost:7180/Entradas>. Para compilar: `dotnet build`.

Si configuras otro equipo, prepara primero el certificado de desarrollo con `dotnet dev-certs https --trust`. El perfil HTTP también está disponible mediante `dotnet run --launch-profile http`, en <http://localhost:5180>.

## SQLite y el visor

- `Data/EntradasMvc.db` es una base SQLite válida y vacía, sin tablas ni registros. Haz clic en ella en el explorador de VS Code para abrirla con **SQLite Viewer**. Si se abre con otro editor, usa **Abrir con… → SQLite Viewer**.
- `appsettings.json` incluye `ConnectionStrings:DefaultConnection` con `Data Source=Data/EntradasMvc.db`.
- El paquete `Microsoft.Data.Sqlite` queda disponible para usar SQLite desde C# cuando se necesite. La cadena está preparada; el cotizador no abre conexiones ni guarda información.
- No se requiere instalar un servidor de base de datos.

