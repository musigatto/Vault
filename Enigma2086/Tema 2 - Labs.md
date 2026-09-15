---
titulo: Tema 2 - Labs (30 min)
curso: Enigma2086
tema: 2
tipo: labs
tags:
  - enigma2086
  - tema2
  - labs
  - password-policies
  - pam
  - gpo
  - spyagent
  - lansweeper
  - google-authenticator
---

# Labs (30min) 1:50

## Lab 1 - 10min+ - Implementing Password Policies Using Windows Group Policy
- Si en el smoothwall no funciona la password (toor), abrirla en una ventana nueva y entonces ya va

## Lab 2 - 10min - Implementing Password Policies in Linux with PAM
- En el punto 25 NO hay que añadir el sudo
- En el punto 30 SI que usamos el sudo, ya que al hacerlo, se ejecuta como root, y se salta las limitaciones de los passwords

## Lab 3 - 10min - Monitoring User Activities on a Remote User System with SpyAgent

## Exercise 1: 30min - Implementing Password Policies Using Windows Group Policy
- En el punto 45, el restart de la máquina, tarda bastante, ¿unos 5minutos?
- Respuesta: ECCPassword Policy

## Exercise 2: 20min - Implementing Password Policies in Linux
- PAM: Es una serie de módulos (librerías), que puedo añadir o modificar al proceso de login, auditoria, etc. Estos módulos me permiten funcionalidades extras como:
	- Permitir el login solo en un determinado periodo de tiempo (de 9:00 a 17:00),
	- desde una IP concreta (la IP de casa del empleado),
	- restringir el consumo de recursos (no pueda consumir mas del 35% de CPU, o el 67% de la red),
	- Añadir el uso de un 2FA, como Google-Authenticator, etc..
- En el punto 15, ya están instalados los paquetes
- En el punto 30, Alice está cambiando la contraseña, pero está utilizando sudo, lo que significa, que realmente lo está ejecutando como root. Esto implica que le deja cambiar la contraseña a una insegura, que no debería dejar si lo hiciera directamente Alice, sin el sudo.
	- Realmente, en el punto 25 no deberiamos usar sudo
- Respuesta: minlength=8

## Exercise 3: 20min - Monitoring Activities on a Remote User System
- En el punto 20 dice que te asegures que Windows Security tiene deshabilitado el antivirus. En el iLab, ya está deshabilitado, no hay que hacer nada
- Respuesta: CND\Administrator

## Exercise 4: NO LO HACEMOS - Asset Discovery using Lansweeper
- La página web es distinta a la que aparece en el Lab, la herramienta no se puede descargar. No podemos hacer este Lab. Si quereis leer que hace, ok, pero lo saltamos.
- Si alguna herramienta os pide registraros con un email, utilizad:
	- https://tempmail.ninja - Este me ha funcionado en este lab
	- https://correotemporal.org/ - No me ha funcionado
	- https://temp-mail.org/es/ - No me ha funcionado
- Respuesta: Total Assets

## Exercise 5: Create and Link a Group Policy Object in Active Directory
- Respuesta: Group Policy Managements // CND.com

## Exercise 6: Implementing password policy using ManageEngine Password Manager
- Respuesta: PMP

## Exercise 7: Implementing Security policies in Linux using Google-Authenticator
- Respuesta: /etc/pam.d/common-auth

## Ver también
- [[Tema 2 - Administrative Network Security]]
- [[Logística iLabs]]
- [[Enigma2086]]