# SonarJobs — app local de un solo archivo

Abre `index.html` en Chrome o Edge sobre Windows. No necesita instalación, cuenta, backend ni base de datos. Requiere internet para consultar feeds y cargar los lectores de PDF/DOCX.

La interfaz está disponible en español, inglés y francés mediante el selector del encabezado. La preferencia se mantiene solo mientras la pestaña está abierta.

## Funciones

- Lee CV PDF, DOCX o TXT dentro del navegador. El texto solo vive en memoria mientras la página está abierta.
- Consulta feeds públicos de Remotive, Remote OK, Jobicy y Arbeitnow; deduplica, filtra y ordena los resultados en el navegador.
- Compara palabras del CV con título, etiquetas y descripción de cada vacante. Muestra los términos coincidentes como evidencia; el porcentaje es similitud textual, no una probabilidad de contratación.
- Prepara una carta breve editable a partir de términos presentes en el CV; permite copiarla o descargarla.
- Abre la publicación original para que la persona complete y envíe directamente al empleador.
- No usa `localStorage`, cookies propias, analítica, cuentas ni servidor de perfiles. Al cerrar la pestaña desaparece el CV y los resultados en memoria.

## Privacidad y red

El documento nunca se sube a SonarJobs ni se incluye en las consultas. Las consultas van a los endpoints de Remotive y Arbeitnow; los campos opcionales de puesto y ubicación se filtran en el navegador y no se envían. PDF.js y Mammoth se descargan desde cdnjs solo cuando se selecciona PDF o DOCX. El acceso a esas fuentes puede revelar la dirección IP al proveedor/CDN, como cualquier solicitud web.

Cada fuente conserva su atribución y enlace de publicación; Remotive, por ejemplo, exige enlazar su vacante original y acredita retrasos de hasta 24 horas. Remote OK y Jobicy permiten feeds públicos, aunque la URL pública normalmente conduce primero al portal de la bolsa y no siempre al formulario ATS. Los puestos, cobertura, disponibilidad de feeds, CORS y términos de cada proveedor pueden cambiar; revisa siempre la oferta original.

## Límite de los envíos externos

Desde un HTML abierto como `file://`, el navegador no puede completar de forma universal formularios de otros dominios: el aislamiento entre sitios, los inicios de sesión, CAPTCHA y los flujos propios de cada ATS lo impiden. Por eso SonarJobs prepara el texto y abre el portal oficial; el candidato revisa y pulsa enviar allí. No usa credenciales, automatización de navegador ni envíos masivos.

Para completar una candidatura sin intervención habría que integrar cada empleador/ATS mediante una API de postulación autorizada, normalmente con OAuth y un backend seguro para proteger credenciales. Eso ya no puede hacerse de forma segura con un único HTML local.

## Alcance

La búsqueda cubre las vacantes expuestas por estos feeds; **no puede listar toda la web**. Muchas empresas y bolsas no ofrecen APIs públicas, y no se raspan páginas protegidas. Este formato escala en distribución (un archivo que cada persona ejecuta localmente), pero no es un servicio centralizado: no almacena CVs ni sincroniza estados entre dispositivos. Añadir más países, bolsas laborales o portales requiere una API/feed permitido por cada fuente.
