---
titulo: Tema 2 - Administrative Network Security
curso: Enigma2086
tema: 2
tipo: teoria
tags:
  - enigma2086
  - tema2
  - administrative-security
  - ceh
  - cnd
---

# Tema 2 - Administrative Network Security

## LO#01: Obtain regulatory frameworks compliance

## LO#02: Discuss various regulatory frameworks, laws, and acts

### PCI DSS - Payment Card Industry – Data Security Standard
- PCI DSS es un estándar de seguridad de alto nivel, indicado para todo el ecosistema de empresas que graban o procesan datos de tarjetas de crédito y débito – cubriendo desde dispositivos electrónicos, hasta aplicaciones e infraestructuras.
- Este estándar fue establecido por PCI Security Standards Council (PCI SSC), formado por las grandes compañías de tarjetas, para tornar el ecosistema de pagos electrónicos más seguro y garantizar la adhesión y confianza de los clientes.
- A pesar de que el alcance de protección de datos del PCI sea menor (datos de tarjetas de pagos), está contenido en el alcance de datos personales de LGPD y de GDPR
- PCI DSS ofrece controles muy concretos que pueden servir como evidencia o referencia para aspectos del artículo 32 del RGPD
	- 🇬🇧 https://iswlegal.com/gdpr/articles/article-32 - Artículo 32
- https://blog.segu-info.com.ar/2020/08/apis-con-certificacion-pci-dss-rgpd-y.html - PCI DSS
- https://www.pcihispano.com/ - PCI DSS Hispano
- https://blog.segu-info.com.ar/2022/04/pci-dss-v40-y-la-proteccion-de-scripts.html - PCI DSS v4.0
- https://blog.segu-info.com.ar/2022/06/analisis-de-pci-dss-v40.html - Análisis de PCI DSS v4.0
- https://www.incibe.es/protege-tu-empresa/blog/pagos-linea-mas-seguros-pci-dss-version-40 - v4.0

### HIPAA - Health Insurance Portability and Accountability Act
- La Ley de Portabilidad y Responsabilidad de Seguros de Salud (HIPAA) de 1996 es una legislación diseñada para facilitar que los trabajadores estadounidenses conserven la cobertura del seguro médico cuando cambian o pierden su trabajo.
- HIPAA protege también la privacidad y le brinda más acceso a su expediente médico.
- https://www.uprm.edu/p/cpshi/ley_hippa - HIPAA

### GDPR - General Data Protection Regulation
- https://eur-lex.europa.eu/ES/legal-content/summary/general-data-protection-regulation-gdpr.html - Reglamento general de protección de datos (RGPD)
- https://certix.es/noticias/normativa/rgpd-reglamento-general-proteccion-datos-guia-completa/ - Guía

### SOX - Sarbanes Oxley
- Aunque la Ley SOX es una normativa estadounidense, afecta a empresas españolas que operan en los mercados financieros de Estados Unidos, y también a proveedores de empresas reguladas por SOX.
- La Ley Sarbanes Oxley se promulgó en Estados Unidos con el propósito de monitorizar a las empresas que cotizan en bolsa de valores, evitando que la valorización de las acciones de las mismas sean alteradas de manera dudosa. Su finalidad es evitar fraudes y riesgo de bancarrota, protegiendo al inversionista.
- https://www.ineaf.es/tribuna/que-es-la-ley-sox-y-para-que-sirve/ - SOX

### GLBA - Gramm-Leach-Bliley Act
- Protege el intercambio de información financiera entre instituciones y bancos, manteniendo los derechos de los usuarios

### Normas ISO serie 27k
- http://iso27000.es/ - El portal de ISO 27001 en Español
	- http://iso27000.es/iso27000.html - Normas ISO 27k
- https://normaiso27001.es/ - Otro portal que habla de las ISO 27k
- ISO/IEC 27000:2026:
	- Es/era un vocabulario estándar para el ISMS / SGSI.
	- Introducción y base para el resto.
	- En la última edición de 2026, se centra mas en conceptos y principios que en la terminología.
- ISO/IEC 27001:2022:
	- Es la certificación que deben obtener las organizaciones.
	- Es la norma más importante de la familia.
	- Norma que especifica los requisitos para la implantación del ISMS / SGSI.
	- Se basa en el conocido "Ciclo de Deming" Plan-Do-Check-Act (PDCA o PHVA) que significa "Planificar-Hacer-Verificar-Actuar" siendo este un enfoque de mejora continua.
	- Adopta un enfoque de gestión de riesgos y promueve la mejora continua de los procesos.
	- Fue publicada como estándar internacional en octubre de 2005. Revisada en septiembre de 2013.
	- Es consistente con las mejores prácticas descritas en ISO/IEC 27002
- ISO/IEC 27002:2022:
	- Proporciona recomendaciones de las mejores prácticas en la gestión de la seguridad de la información a todos los interesados y responsables en iniciar, implantar o mantener sistemas de gestión de la seguridad de la información.
	- Es la guía recomendada de implantación de la 27001

### DMCA - Digital Millennium Copyright Act
- Copyrigth
- https://es.wikipedia.org/wiki/Digital_Millennium_Copyright_Act - DMCA

### FISMA - Federal Information Security Management Act
- La certificación FISMA es un requisito para muchos contratos con el gobierno de Estados Unidos, siendo un marco diseñado para proteger al gobierno de los Estados Unidos contra los ataques a la ciberseguridad y los desastres naturales que pongan en riesgo los datos confidenciales, las operaciones y los activos.
- Obliga a implementar y soportar controles de seguridad de TI uniformes, definidos por el Instituto Nacional de Normas y Tecnología (NIST), permitiendo entre otras cosas, que los contratistas trasladen, de manera segura y confidencial, sus aplicaciones indispensables a la nube, ambientes de hospedaje administrados y que contraten a proveedores de SaaS que cumplan con las disposiciones de la ley FISMA.

## LO#03: Learn to design and develop security policies
- Tipos de Políticas de Seguridad
	- Enterprise Information Security Policy (EISP): Centrado en las políticas de seguridad de la empresa.
	- Issue Specific Security Policy (ISSP): Centrado en el uso de tecnologías.
		- Se utiliza para añadir información adicional sobre la postura general de seguridad.
		- Ayuda a proporcionar orientación detallada y específica para instruir a las organizaciones en el uso seguro de sistemas tecnológicos.
		- Esta política sirve para proteger a empleados y organizaciones de la ineficiencia o ambigüedad.
	- System Specific Security Policy (SSSP): Centrado en configurar y mantener sistemas.

## LO#04: Conduct security awareness training

## LO#05: Discuss other administrative security measures

## LO#06: Discuss asset management
- https://invgate.com/es/itsm/it-asset-management - ITAM

## LO#07: Learn how to stay up to date on security trends and threats

### Noticias
- https://www.redeszone.net/ - Tienen una subsección especializada en seguridad. Muy activo.
- https://blog.segu-info.com.ar/ - Argentino, muy activo.
- https://thehackerway.com/ - Español, premiado como mejor blog técnico europeo en 2021 en la categoría de ciberseguridad.
- https://derechodelared.com/ - Ciberseguridad, Privacidad, Derecho de las TIC

### Eventos en España
- https://www.google.com/maps/d/edit?mid=1eDUrpB8zlGJPifXa7hddG493sNk623I&usp=sharing - Mapa con todos los eventos de ciberseguridad y hacking en España
- https://wiki.securiters.com/securiters-wiki/congresos-de-ciberseguridad - Congresos de Ciberseguridad
- https://hackandbeers.es/ - Hack & Beer

## Ver también
- [[Tema 2 - Labs]]
- [[Tema 1 - Network Attacks and Defense Strategies]]
- [[Enigma2086]]