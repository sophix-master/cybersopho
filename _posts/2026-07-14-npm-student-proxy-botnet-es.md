---
layout: default
title: "La Botnet Silenciosa en el Navegador: Cómo 148 Proxies Falsos de npm Weaponizaron la Curiosidad Estudiantil"
date: 2026-07-14
description: "Análisis de una campaña reciente donde paquetes maliciosos de npm, disfrazados de proxies web para estudiantes, evadieron los escáneres tradicionales de la cadena de suministro para convertir los navegadores en una botnet DDoS, destacando el cambio crítico hacia ataques de ejecución del lado del cliente."
---

<a href="/2026/07/14/npm-student-proxy-botnet/" class="lang-switch">🇬🇧 Read in English</a>

<div class="post-header">
    <span class="post-date">14 de julio de 2026</span>
    <h1>La Botnet Silenciosa en el Navegador: Cómo 148 Proxies Falsos de npm Weaponizaron la Curiosidad Estudiantil</h1>
</div>

<div class="post-content" markdown="1">

<p>En mayo de 2026, una campaña sofisticada desplegó 148 paquetes de npm disfrazados de proxies web para estudiantes, transformando con éxito los navegadores de usuarios desprevenidos en una botnet de denegación de servicio distribuida (DDoS). Este incidente destaca una evolución peligrosa en los ataques a la cadena de suministro: el cambio de comprometer la tubería de compilación a weaponizar la ejecución del lado del cliente.</p>

<h3>1. El abuso "inocente" del registro</h3>
<p>Las herramientas tradicionales de Análisis de Composición de Software (SCA) y Pruebas de Seguridad de Aplicaciones Estáticas (SAST) están diseñadas para detectar código malicioso en el momento de la instalación. Esta campaña evadió por completo esos controles. Los paquetes no contenían ganchos de ciclo de vida ni scripts de compilación nativos. En su lugar, actuaron meramente como alojamiento gratuito para una aplicación web del lado del cliente, esperando en silencio hasta que un usuario visitó activamente el sitio proxy para evadir los filtros de red escolares.</p>

<h3>2. La vulnerabilidad de la rama mutable</h3>
<p>Una vez que el proxy se cargó en el navegador, ejecutó un cargador de scripts remoto que obtenía JavaScript de un repositorio de GitHub a través de una CDN. Críticamente, esta solicitud apuntaba a una rama principal mutable sin ninguna verificación de Integridad de Subrecursos (SRI). Esto permitió a los operadores cambiar la carga útil en silencio a voluntad, ejecutando código con los privilegios de origen del propio sitio proxy y con acceso completo a las cookies y al almacenamiento local.</p>

<h3>3. Agotamiento del plano de control sobre inundación volumétrica</h3>
<p>Si bien la botnet lanzó inundaciones HTTP crudas, su módulo más sofisticado utilizó el protocolo proxy Wisp para abrir cientos de conexiones WebSocket por navegador. No se trató de un ataque volumétrico tradicional; fue un ataque al plano de control diseñado para agotar los descriptores de archivos e inundar el almacenamiento de registros en el servidor Wisp objetivo, colapsando efectivamente la infraestructura a través de un ciclo legítimo de creación y cierre de conexiones.</p>

<div class="highlight-box">
<strong>4. La ingeniería social de la rebelión:</strong> El verdadero genio de este ataque fue su vector psicológico. No se dirigió a los desarrolladores; se dirigió a los adolescentes. Al ofrecer una herramienta funcional para evadir los restrictivos filtros web escolares, los atacantes aprovecharon el deseo natural de libertad digital y rebeldía. Los usuarios abrieron la trampa voluntariamente, creyendo que estaban burlando al sistema, mientras se convertían inconscientemente en el arma.
</div>

<h3>5. Defensas estratégicas para una amenaza del lado del cliente</h3>
<p>Mitigar esta clase de ataque requiere ir más allá del análisis estático de código. Las organizaciones e instituciones educativas deben implementar Políticas de Seguridad de Contenido (CSP) estrictas para bloquear la ejecución no autorizada de scripts entre orígenes. Además, aplicar la Integridad de Subrecursos (SRI) para todos los scripts externos y desplegar bloqueos a nivel de DNS para hosts de scripts y monetización maliciosos conocidos son controles de línea base innegociables. Para los usuarios afectados, limpiar la caché del navegador, el almacenamiento local y anular el registro de los service workers persistentes es la única forma de romper el mecanismo de persistencia.</p>

<p>Mientras los registros de paquetes públicos puedan ser abusados como Redes de Entrega de Contenido (CDN) gratuitas para aplicaciones del lado del cliente, la superficie de ataque seguirá expandiéndose mucho más allá del entorno de compilación tradicional. Los defensores deben adaptar su monitoreo para detectar comportamientos anómalos en tiempo de ejecución, no solo vulnerabilidades estáticas en el código.</p>

<div class="source-link">
<strong>Fuente:</strong><br>
<a href="https://thehackernews.com/2026/07/148-npm-packages-disguised-as-student.html" target="_blank">The Hacker News: 148 npm Packages Disguised as Student Proxies Turned Browsers Into a DDoS Botnet</a><br>
<a href="https://cybersopho.top" target="_blank">https://cybersopho.top</a>
</div>

</div>