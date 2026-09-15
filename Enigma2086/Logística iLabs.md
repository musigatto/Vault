---
titulo: Logística iLabs
curso: Enigma2086
tipo: logistica
tags:
  - enigma2086
  - ilabs
  - logistica
  - curso
---

# Logística iLabs

## Plataformas y acceso
- https://aspen.eccouncil.org/ - Página del curso, de EC Council, material accesible durante 1 año.
	- IMPORTANTE: Hay que aceptar las cookies en esta página, ya que a través de dichas cookies, se enlaza con el material del curso en otra páqina, y con los iLabs también en otra distinta.
- https://support.vitalsource.com/hc/en-us/articles/201344733-Bookshelf-Download-Options - Clientes para acceder al material del curso.
	- https://support.vitalsource.com/hc/en-us/articles/360014105113-iOS-iPadOS - Clientes
- https://ilabs.eccouncil.org/ethical-hacking-exercises/ - iLabs del curso, acceso durante 6 meses. Podéis guardar el estado intermedio de un lab durante 7 días, pero solo dos al mismo tiempo.
	- Hay que registrarse desde: https://eccouncil.learnondemand.net/User/Register?OrganizationId=1133
	- https://eccouncil.learnondemand.net/ - URL directa a los iLabs
	- Los laboratorios hay que hacerlos en un navegador derivado de Chromium. Navegadores derivados de Firefox dan problemas
	- https://github.com/Duffer-9533/CEH-V13 - Respuestas a los Labs
	- Los Labs tienen un tiempo predeterminado, que cuando se acaba sale de los mismos. Cuando quedan exactamente 10 minutos para acabar, te da la posibilidad de aumentar el tiempo en otros 30 minutos.
	- Si alguna herramienta os pide registraros con un email, utilizad:
		- https://correotemporal.org/
		- https://temp-mail.org/es/

## Teclado Americano
- https://upload.wikimedia.org/wikipedia/commons/5/51/KB_United_States-NoAltGr.svg
- https://en.wikipedia.org/wiki/British_and_American_keyboards
- Se puede con el teclado en pantalla del Windows, no el del entorno de iLabs

## Comandos interesantes

### Linux
- Para cambiar a root en Linux:  sudo -i
- Para cambiar el teclado en Ubuntu al teclado español, hay varias formas, pero la primera debería funcionar sin problemas:
	- Posibilidad 1:
		- Abre la Configuración del sistema
		- Selecciona Entrada de texto
		- Pulsa en el icono del símbolo +
		- Añade Español
		- Ahora elimina el inglés o el otro idioma que tengas seleccionado
		- Cerramos esa ventana
	- Posibilidad 2: ejecutar lo siguiente:
		- setxkbmap es
	- Posibilidad 3: ejecutar lo siguiente:
		- sudo dpkg-reconfigure keyboard-configuration
- https://www.kali.org/tools/all-tools/ - Herramientas incluidas en Kali
	- apt update ; apt upgrade theHarvester # Para actualizar alguna herramienta concreta en el Parrot
- https://openwebinars.net/blog/15-atajos-teclado-mas-utilizados-shell-linux/ - Atajos de teclado en la shell de Linux (bash)

### Windows
- Para ver los nombres de los interfaces en Windows:  netsh interface show interface
- Para cambiar el teclado en Windows 11:
	- Buscar "keyboard" en el buscador de la barra
	- Pinchar en "Edit language and keyboard options"
	- Añadir Spanish (España)
	- Pinchar abajo donde pone "Choose an input method to always use as default"
	- Elegir teclado español
	- OTRO
		- Settings
		- Time & Language
			- Language & region
			- Add Language
			- Español (España)
			- Elegimos solo el primer campo
			- Cuando acabe, volvemos atras y seguimos con lo siguiente
		- Typing
		- Advance keyboard settings
		- Spanish
- Para cambiar el teclado en el Windows Server 2016:
	- Buscar "language" en el buscador de la barra
	- Pinchar en "Language" en el desplegable
	- Pinchamos en "options", a la derecha del cuadrito que pone "English (United States)"
	- Añadimos teclado Spanish (España) como "Input Method", pinchando en "Add an input method"
	- Quitamos Inglés como "Input Method"
	- Grabamos y salimos
- Para copiar y pegar texto a la Máquina virtual, arriba a la izquierda, en la ventana de Guacamole, tenemos un rayito. Pinchando en el rayo --> Type Text --> Type Clipboard Text , podemos poner el texto que se mandará a la máquina virtual.

## Ver también
- [[Tema 1 - Labs]]
- [[Tema 2 - Labs]]
- [[Examen CEH Practical]]
- [[Logística del Curso]]
- [[Enigma2086]]