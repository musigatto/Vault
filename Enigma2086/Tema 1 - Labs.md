---
titulo: Tema 1 - Labs (40 min)
curso: Enigma2086
tema: 1
tipo: labs
tags:
  - enigma2086
  - tema1
  - labs
  - sql-injection
  - xss
  - nmap
  - brute-force
---

# Labs (40min)

## Lab 1 - 10min - Understanding the Working of SQL Injection Attacks
- Ejemplo: SELECT Count(*) FROM Users WHERE UserName='Blah' or 1=1 --' AND Password='Springfield'
- La @ en el teclado americano, son las comillas dobles en el teclado español, esto es, shift+2
- En la máquina Linux, para poner el teclado en español, usamos el comando:
	- sudo setxkbmap es
- Cuando se ejecuta la orden sqlmap, hay que anteponerle sudo
- CUIDADO al cortar y pegar el comando, las comillas dobles no son aptas para la linea de comandos, hay que borrarlas y volver a ponerlas.
- Si en algún comando sqlmap se queda mucho rato pensando, hay que darle a Enter
- En el sistema, la contraseña del usuario bob es user@123
- En la página web, la contraseña del usuario Bob es Passw0rd
- En el punto 27, NO debería haber un espacio en blanco en la URL, entre Id=ORD-001

## Lab 2 - 10min - Understanding the Working of XSS Attacks

## Lab 3 - 10min - Understanding the Working of Network Scanning Attkacs
- En este lab usamos nmap
- El scan de tipo Xmas no detecta nada, porque no funciona con máquinas de tipo Windows

## Lab 4 - 10min - Understanding the Working of Brute Force Attacks

## Ver también
- [[Tema 1 - Network Attacks and Defense Strategies]]
- [[Logística iLabs]]
- [[Enigma2086]]