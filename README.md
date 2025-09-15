https://imgs.search.brave.com/s7mKgNef5gQqiHr_IhotkWvT36P4Na6zFxlyY9IcLO0/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly91cGxv/YWQud2lraW1lZGlh/Lm9yZy93aWtpcGVk/aWEvY29tbW9ucy90/aHVtYi9lL2U5L1ZT/Q29kaXVtLnN2Zy8y/NTBweC1WU0NvZGl1/bS5zdmcucG5n

Binarios de software de código abierto gratuitos y libres de Visual Studio Code
lanzamiento actual licencia Gitter codio codio

estado de compilación (linux) estado de compilación (macos) estado de compilación (ventanas)

Esto no es un tenedor. Este es un repositorio de scripts para crear automáticamente De Microsoft vscode repositorio en binarios con licencia libre con una configuración predeterminada impulsada por la comunidad.

Tabla de contenidos
Descargar/Instalar
Instalar con Brew
Instalar con Windows Package Manager (WinGet)
Instalar con Chocolatey
Instalar con Scoop
Instalar con snap
Instalar con Package Manager
Instalar en Arch Linux
Opción Flatpak
Construir
¿Por qué existe esto
Más información
Plataformas compatibles
Descargar/Instalar
🎉 🎉 Descargue la última versión aquí: estable o insiders 🎉 🎉

Más información / consejos útiles están aquí.

Instalar con Brew (Mac)
Si estás en una Mac y tienes Cerveza casera instalado:

# stable
brew install --cask vscodium

# insiders
brew install --cask vscodium@insiders
Instalar con Windows Package Manager (WinGet)
Si usa Windows y tiene Administrador de paquetes de Windows instalado:

:: stable
winget install -e --id VSCodium.VSCodium

:: insider
winget install -e --id VSCodium.VSCodium.Insiders
Instalar con Chocolatey (Windows)
Si usa Windows y tiene Chocolate instalado (gracias a @Thilas):

:: stable
choco install vscodium

:: insider
choco install vscodium-insiders
Instalar con Scoop (Windows)
Si usa Windows y tiene Scoop instalado:

scoop bucket add extras
scoop install vscodium
Instalar con snap (GNU/Linux)
VSCodium está disponible en el Tienda Snap como Codio, gracias a la ayuda de la Snapcrafters comunidad. Si su distribución GNU/Linux tiene soporte para snaps:

snap install codium --classic
Instalar con Package Manager (GNU/Linux)
Siempre puedes instalarlo usando las descargas (deb, rpm, tar) en la página de lanzamientos estable o insiders, pero también puedes instalarlo usando tu administrador de paquetes favorito y obtener actualizaciones automáticas.

@paulcarroty ha configurado un repositorio con instrucciones para apt, dnf y zypper aquí.

Cualquier problema al instalar VSCodium usando su administrador de paquetes debe dirigirse al rastreador de problemas de ese repositorio.

Instalar en Arch Linux
VSCodium está disponible en AUR, mantenido por @binex-dsk como paquete vscodium-bin (estable) y como contenedor de información privilegiada de vscodium.

Si desea ahorrar espacio en disco haciendo que VSCodium utilice Electron en todo el sistema, también debe vscodio-electrón, mantenido por @m00nw4tch3r.

Un paquete alternativo vscodium-git, mantenido por @cedricroijakkers, también está disponible si desea compilar desde la fuente usted mismo.

Opción Flatpak (GNU/Linux)
VSCodium está disponible como aplicación Flatpak aquí y el repositorio de compilación es aquí. Si su distribución tiene soporte para flatpak, y has habilitado el repositorio de flathub:

flatpak install flathub com.vscodium.codium
flatpak run com.vscodium.codium
Construir
Se pueden encontrar instrucciones de compilación aquí

¿Por qué existe esto
Este repositorio contiene archivos de compilación para generar binarios de lanzamiento gratuito de Visual Studio Code de Microsoft. Cuando hablamos de “software libre”, hablamos de libertad, no de precio.

Las versiones de Visual Studio Code de Microsoft tienen licencia bajo Esta licencia no es FLOSS y contienen telemetría/seguimiento. Según este comentario desde un mantenedor de Visual Studio Code:

Cuando [Microsoft] creamos Visual Studio Code, hacemos exactamente esto. Clonamos el repositorio vscode, establecemos un product.json personalizado que tiene una funcionalidad específica de Microsoft (telemetría, galería, logotipo, etc.) y luego producimos una compilación que lanzamos bajo nuestra licencia.

Cuando clona y compila desde el repositorio vscode, ninguno de estos puntos finales está configurado en el product.json predeterminado. Por lo tanto, genera una compilación "limpia", sin las personalizaciones de Microsoft, que por defecto tiene la licencia MIT

Este repositorio existe para que no tengas que descargar+compilar desde la fuente. Los scripts de compilación en este repositorio clonan el repositorio vscode de Microsoft, ejecutan los comandos de compilación y cargan los binarios resultantes en Lanzamientos de GitHub. Estos binarios están licenciados bajo la licencia MIT. La telemetría está deshabilitada.

Si quieres construir desde el código fuente tú mismo, dirígete a Repositorio vscode de Microsoft y seguir sus instrucciones. Este repositorio existe para facilitar la obtención de la última versión de Visual Studio Code con licencia MIT.

El proceso de compilación de Microsoft (que estamos ejecutando para compilar los binarios) descarga archivos adicionales. Los paquetes descargados durante la compilación son:

Extensiones prediseñadas desde GitHub:
ms-vscode.js-debug-companion
depuración de ms-vscode.js
ms-vscode.vscode-js-tabla-de-perfil
Desde Liberaciones de electrones (usando gulp-átomo-electrón)
electrón
ffmpeg
Más información
Documentación
Para obtener más información sobre cómo desactivar toda la telemetría, consejos para migrar de Visual Studio Code a VSCodium y más, consulte La página de documentos página.

Solución de problemas
Si tiene algún problema, verifique La página de solución de problemas o los problemas existentes.

Las extensiones y el mercado
Según Visual Studio Marketplace Condiciones de uso, Solo puede instalar y utilizar ofertas de Marketplace con productos y servicios de Visual Studio. Por este motivo, VSCodium utiliza open-vsx.org, un registro de código abierto para extensiones de Visual Studio Code. Ver el Extensiones + Marketplace sección en la página Documentos para más detalles.

Tenga en cuenta que algunas extensiones de Visual Studio Code tienen licencias que restringen su uso a las compilaciones oficiales de Visual Studio Code y, por lo tanto, no funcionan con VSCodium. Ver esta nota en la página de Documentos para ver lo que se ha encontrado hasta ahora y posibles soluciones alternativas.

¿Cómo se construyen los binarios de VSCodium?
Si desea ver los comandos que ejecutamos para compilar vscode En los binarios de VSCodium, eche un vistazo a los archivos de flujo de trabajo en .github/workflows para Windows, GNU/Linux y macOS. Estos archivos de compilación llaman a todos los demás scripts del repositorio. Si encuentras algo que no tiene sentido, no dudes en preguntar al respecto en Gitter.

Las compilaciones se ejecutan todos los días, pero salen antes si no hay una nueva versión de Microsoft.

Plataformas compatibles
La versión mínima está limitada por el componente principal Electron, es posible que desees comprobarlo Requisitos previos de la plataforma.

 macOS (zip, dmg) macOS 10.15 o posterior x64
 macOS (zip, dmg) macOS 11.0 o arm64 más nuevo
 GNU/Linux x64 (deb, rpm, AppImage, snap, tar.gz)
 GNU/Linux arm64 (deb, rpm, snap, tar.gz)
 GNU/Linux armhf (deb, rpm, tar.gz)
 GNU/Linux riscv64 (tar.gz)
 GNU/Linux loong64 (tar.gz)
 GNU/Linux ppc64le (tar.gz)
Windows 10 / Server 2012 R2 o posterior x64
Windows 10 / Server 2012 R2 o más reciente arm64
Agradecimientos especiales
@jaredreich	para el logo
@PalinuroSec	para CDN y nombre de dominio
Logotipo de MacStadium	para proporcionar un Mac mini M1
@daiyam	para certificado macOS
Logotipo de SignPath	firma de código gratuita en Windows proporcionada por SignPath.io, certificado por Fundación SignPath
Licencia
MIT
