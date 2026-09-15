---
titulo: Tema 1 - Network Attacks and Defense Strategies
curso: Enigma2086
tema: 1
tipo: teoria
tags:
  - enigma2086
  - tema1
  - network-security
  - ceh
  - cnd
---

# Tema 1 - Network Attacks and Defense Strategies

## LO#01: Explain essential terminologies related to network security attacks
- https://hackernoon.com/introducing-the-infosec-colour-wheel-blending-developers-with-red-and-blue-security-teams-6437c1a07700 - Los colores de la ciberseguridad: Blue, Red, Purple, Orange...
- https://www.xataka.com/seguridad/esta-empresa-tenia-158-anos-700-empleados-contrasena-debil-clic-bastaron-para-llevarla-a-bancarrota - Esta empresa tenía 158 años y más de 700 empleados. Una contraseña débil y un clic bastaron para llevarla a la bancarrota
- Risk = Asset + Threat + Vulnerability
- Attack = Motive (Goal) + Method (TTPs) + Vulnerability
- TTP: Las técnicas son las herramientas utilizadas, la táctica es la forma de combinar esas herramientas para hacer un determinado trabajo y el procedimiento es la guía a seguir para hacer el trabajo.

## LO#02: Describe the various examples of network-level attack techniques

## LO#03: Describe the various examples of application-level attack techniques
- XSS, CSRF
- &pct-off=60-99 - Truco para añadir a la URL de amazon para ver los productos con un descuento dado
- OWASP Top 10
	- https://top10.owasp.org/2025/es/ - OWASP Top 10 2025
	- https://blog.segu-info.com.ar/2025/11/owasp-top-10-2025-rc-si-al-fin-salio.html - OWASP Top 10 2025
	- https://ahsan.au/a102025-mishandling-exceptional-conditions/ - A10:2025 - Nueva categoría: Fallo al manejar situaciones excepcionales.
		- La gestión inadecuada de condiciones de excepción es una nueva categoría para 2025. Esta categoría contiene 24 CWE centrados en la gestión inadecuada de errores, errores lógicos, fallos abiertos y otros escenarios relacionados derivados de condiciones anómalas que pueden experimentar los sistemas.

## LO#04: Describe the various examples of social engineering attack techniques

## LO#05: Describe the various examples of email attack techniques

## LO#06: Describe the various examples of mobile device-specific attack techniques

## LO#07: Describe the various examples of cloud-specific attack techniques
- OWASP Top 10 Cloud Security Risks

## LO#08: Describe the various examples of wireless network-specific attack techniques

## LO#09: Describe the various examples of Supply Chain Attack techniques
- https://top10.owasp.org/2025/es/A03_2025-Software_Supply_Chain_Failures/ - Fallas en la Cadena de Suministro de Software
- https://www.muycomputerpro.com/2022/01/17/desarrollador-corrompe-librerias-comunidad-mantendra-una - El autor lo planteó como una protesta contra el modelo de open source, diciendo esencialmente que nadie revisaba lo que publicaba y que las corporaciones dependían ciegamente de código que él mantenía gratis.
- https://xkcd.com/2347/ - La cadena de suministro en el mundo actual
- https://cryptobriefing.com/komodo-developers-hacked-users/ - Ataque a Komodo Wallet
- https://blog.tecnetone.com/el-ciberataque-de-solarwinds-un-caso-de-estudio - El ataque SolarWinds
	- https://www.muyseguridad.net/2021/03/02/solarwinds123-contrasenas/ - Contraseña solarwinds123

## LO#10: Describe attacker hacking methodologies and frameworks
- EC Council
	- Reconnaissance
	- Scanning
		- Enumeration
		- Vulnerabilities
	- Gaining access
	- Maintaining access
	- Clearing tracks
- https://www.hornetsecurity.com/es/knowledge-base/cyber-kill-chain/ - Cyber Kill Chain
- MITRE
	- https://attack.mitre.org/ - ATT&CK
	- https://blog.segu-info.com.ar/2025/01/mitre-lanza-d3fend-10-para-estandarizar.html - MITRE lanza D3FEND 1.0 para estandarizar técnicas de defensa
		- https://d3fend.mitre.org/ - D3FEND
	- https://aadapt.mitre.org/ - MITRE AADAPT (Adversarial Actions in Digital Asset Payment Technologies)
	- https://atlas.mitre.org/ - MITRE ATLAS (Adversarial Threat Landscape for Artificial-Intelligence Systems) is a globally accessible, living knowledge base of adversary tactics and techniques against Al-enabled systems based on real-world attack observations and realistic demonstrations from Al red teams and security groups.
	- https://blog.segu-info.com.ar/2019/08/la-filosofia-de-att-explicada.html - Artículo pequeño
	- https://blog.segu-info.com.ar/2019/06/matrices-y-herramientas-de-mitre-att.html - Estupendo artículo (largo)

## LO#11: Understand fundamental goal, benefits, and challenges in network defense
- Information Assurance (IA):
	- Es la práctica de asegurar la información y gestionar los riesgos relacionados con el uso, el procesamiento, el almacenamiento y la transmisión de la información.
	- La garantía de la información incluye la protección de la integridad, la disponibilidad, la autenticidad, el no repudio y la confidencialidad de los datos de los usuarios.
	- La IA abarca no sólo las protecciones digitales sino también las técnicas físicas. Estas protecciones se aplican a los datos en tránsito, tanto en forma física como electrónica, así como a los datos en reposo.

## LO#12: Explain continual/adaptive security strategy
- Protect, Detect, Respond, Predict
- Acercamientos a la seguridad de red.
	- Preventivo
	- Reactivo, incluye monitorización
	- Retrospectivo, incluye forensic, CSIRT, CERT
	- Proactivo, incluye Threat Intelligence y Risk Assessment. Consiste en mejorar los protocolos y técnicas de cara a futuros ataques.
- Estrategia de seguridad Continua/Adaptativa
	- Proteger, Defensa en profundidad
	- Detectar, Monitorización.
	- Responder, Repuesta a Incidentes.
	- Predecir, Threat Intelligence, Risk Assessment

## LO#13: Explain defense-in-depth security strategy
- https://www.youtube.com/results?search_query=atm+robbery - Robo de cajero
	- https://www.elmundo.es/espana/2022/12/28/63ac5f33fc6c8309128b4591.html - Y en Badajoz, con el mismo método

## Ver también
- [[Tema 1 - Labs]]
- [[Tema 2 - Administrative Network Security]]
- [[Enigma2086]]