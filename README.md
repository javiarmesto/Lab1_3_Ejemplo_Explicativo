# Guía de instalación y configuración

## Antes de empezar

Demostración Copilot para **proponer sustitutos de artículos**: genera propuestas en un PromptDialog y permite revisar/confirmar sustituciones.

**Referencia del checkout:** `application 26.0.0.0`, `runtime 15.0`; extensión `2-ItemSubstitution Demo` versión `0.10.0.0`. Es la configuración del manifiesto, no una prueba de compatibilidad con otros entornos.

1. Clona `https://github.com/javiarmesto/Lab1_3_Ejemplo_Explicativo.git` y abre la carpeta en VS Code con AL Language.
2. Configura tu sandbox en `.vscode/launch.json` (créalo si falta), comprueba las dependencias de [app.json](app.json) y descarga símbolos con **AL: Download Symbols**.
3. Compila con `Ctrl+Shift+B`; publica en el sandbox con `F5` cuando hayas completado la configuración específica del ejemplo.
4. Abre las sustituciones de un artículo y la acción **Suggest with Copilot (Demo Workshop)**. Tras configurar autorización y datos, revisa la propuesta antes de confirmar.

**Mapa del ejemplo:** `CopilotCodeunits/`: generación y capacidad; `Internals/`: almacenamiento/configuración e integración; `PromptDialog/`: propuesta; `Test/`: escenarios de sustitución.

**Límites:** Requiere AI Test Toolkit 26.0.0.0 según el manifiesto. La demostración no es para producción; las pruebas AI necesitan entorno y configuración propios. La revisión documental del 6 de octubre de 2026 es estática; no acredita compilación, publicación ni llamadas a servicios externos.


Esta guía te ayudará a crear y ejecutar la aplicación desde cero. Sigue los pasos cuidadosamente. Si tienes dudas, consulta las ayudas incluidas en cada sección.

## 1. Clonar o copiar el repositorio

Puedes clonar este repositorio usando Git o descargarlo como un archivo ZIP y extraerlo en tu equipo.

**Opción 1: Clonar con Git**
```powershell
git clone https://github.com/javiarmesto/Lab1_3_Ejemplo_Explicativo.git
```

**Opción 2: Descargar ZIP**
- Haz clic en el botón "Code" y selecciona "Download ZIP".
- Extrae el contenido en una carpeta de tu elección.

## 2. Abrir el proyecto en Visual Studio Code

Abre Visual Studio Code y selecciona la carpeta del proyecto.

## 3. Instalar extensiones necesarias

Asegúrate de tener instaladas las siguientes extensiones:
- **AL Language** (de Microsoft)
- **Azure Account** (si vas a usar capacidades de Azure OpenAI)

Puedes instalarlas desde la barra lateral de extensiones de VS Code.

## 4. Descargar símbolos y comprobar dependencias

1. Abre el archivo `app.json` y revisa las dependencias.
2. Presiona `Ctrl+Shift+P` y ejecuta el comando `AL: Download Symbols`.
3. Si falta alguna dependencia, instálala desde el marketplace o consulta con tu instructor.

**Ayuda:** Si tienes errores de símbolos, revisa que la versión de tu servidor Docker o Business Central sea compatible.

## 5. Configurar la conexión a Azure OpenAI

Para usar tu propia capacidad de Azure OpenAI:

1. Abre la codeunit responsable de la configuración de Azure OpenAI (por ejemplo, `SecretsAndCapabilitiesSetup.Codeunit.al`).
2. Busca la sección donde se configuran los parámetros de Azure OpenAI (como endpoint, API key, deployment name, etc.).
3. Configura endpoint, deployment y secreto mediante las funciones de `IsolatedStorageWrapper.Codeunit.al` en tu copia. Los getters fallan si no existe configuración; no pegues secretos en código versionado.

**Ayuda:** Si no tienes una cuenta de Azure OpenAI, puedes crear una desde el portal de Azure: https://portal.azure.com y solicitar acceso a Azure OpenAI en https://aka.ms/oai/access.

## 6. Compilar y publicar la extensión

1. Presiona `Ctrl+Shift+B` para compilar el proyecto.
2. Usa `F5` para publicar y depurar la extensión en tu entorno de Business Central.

**Ayuda:** Si tienes problemas de publicación, revisa la configuración de tu archivo `launch.json`.

## 7. Probar la funcionalidad

- Accede a las páginas y funcionalidades añadidas por la extensión (por ejemplo, desde el menú de Business Central).
- Realiza pruebas siguiendo los escenarios sugeridos en la carpeta `Test/`.

## Consejos y recursos adicionales

- Consulta la documentación oficial de [AL Language](https://docs.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/) para resolver dudas de sintaxis.
- Si tienes problemas con Azure OpenAI, revisa la [documentación de Azure OpenAI](https://learn.microsoft.com/azure/cognitive-services/openai/).
- Pide ayuda a tu instructor si te atascas.

---

¡Suerte! Recuerda que el objetivo es aprender y experimentar. No dudes en investigar y probar diferentes configuraciones.
