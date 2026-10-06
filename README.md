# Guía de instalación y configuración

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
3. Sustituye los valores de ejemplo por los de tu propia cuenta de Azure OpenAI.

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
