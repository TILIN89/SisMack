<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SisMack - Alertas Sísmicas</title>
  <style>
    /* Estilos generales */
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      margin: 0;
      padding: 0;
      overflow-x: hidden; /* Evita la barra de desplazamiento horizontal */
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
    }

    /* Estilos de encabezado */
    .header {
      background-color: #000; /* Color negro */
      color: #fff;
      padding: 10px 0;
      position: fixed;
      width: 100%;
      z-index: 1000;
      top: 0;
      left: 0;
      transition: background-color 0.3s ease;
    }

    .header .container {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 24px;
      margin: 0;
      color: #fff;
      text-decoration: none;
    }

    .nav-list {
      list-style-type: none;
      margin: 0;
      padding: 0;
    }

    .nav-list li {
      display: inline;
      margin-right: 20px;
    }

    .nav-list li a {
      color: #fff;
      text-decoration: none;
      transition: color 0.3s ease;
    }

    .nav-list li a:hover {
      color: #ffd700;
    }

    /* Estilos de sección */
    .section {
      padding: 80px 0;
    }

    .section-title {
      font-size: 36px;
      color: #000;
      margin-bottom: 30px;
    }

    /* Estilos de pie de página */
    .footer {
      background-color: #ff6666; /* Color rojo más suave */
      color: #fff;
      padding: 20px 0;
      text-align: center;
    }

    .footer p {
      margin: 0;
    }

    /* Estilos del mapa */
    #mapa {
      width: 100%;
      height: 400px;
      border-radius: 10px;
      overflow: hidden;
      margin-top: 30px;
    }

    /* Estilos del texto informativo */
    .texto-informativo {
      margin-top: 20px;
      font-size: 18px;
      color: #555;
      text-align: center;
      padding: 10px;
      background-color: #f0f0f0;
      border-radius: 5px;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    }

    /* Estilos del texto de información adicional */
    .info-adicional {
      margin-top: 10px;
      font-size: 14px;
      color: #777;
      text-align: center;
    }

    /* Estilos para resaltar la hora actual */
    .hora-actual {
      font-weight: bold;
    }
  </style>
</head>
<body>
  <header class="header">
    <div class="container">
      <h1 class="logo">SisMack</h1>
      <nav class="navbar">
        <ul class="nav-list">
          <li><a href="#inicio">Inicio</a></li>
          <!-- Cambio: Enlace de alertas como botón -->
          <li><a href="http://127.0.0.1:12472/main/0/storage/emulated/0/Download/Canva/Alertas.html" target="_blank" class="btn">Alertas</a></li>
          <li><a href="#acerca">Acerca de</a></li>
          <li><a href="#contacto">Contacto</a></li>
        </ul>
      </nav>
    </div>
  </header>
    </div>
  </header>
  <section id="inicio" class="section">
    <div class="container">
      <h2 class="section-title">Inicio</h2>
      <p>Bienvenido a SisMack, tu plataforma de alertas sísmicas confiable.</p>
      <!-- Texto informativo -->
      <div class="texto-informativo">
        Estamos monitoreando México en tiempo real para brindarte información precisa sobre alertas sísmicas. <span class="hora-actual" id="hora-actual"></span>
      </div>
      <!-- Mapa de Google Maps centrado en México -->
      <iframe
        id="mapa"
        width="100%"
        height="400"
        frameborder="0"
        style="border:0"
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d17185715.571834937!2d-105.14831580544512!3d23.632486995296716!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x85d1fc56ea3e27c7%3A0xe71e61c7cb9922a7!2sMexico!5e0!3m2!1sen!2sus!4v1624294916798!5m2!1sen!2sus"
        allowfullscreen
      ></iframe>
      <!-- Información proporcionada por SASMEX -->
      <div class="info-adicional">
        Información proporcionada por SASMEX
      </div>
    </div>
  </section>
  <!-- Más secciones como alertas, acerca de, contacto, etc. -->
  <footer class="footer">
    <div class="container">
      <p>&copy; 2024 SisMack. Todos los derechos reservados.</p>
    </div>
  </footer>

  <!-- Script de JavaScript para obtener la hora actual -->
  <script>
    // Obtener la referencia al elemento donde se mostrará la hora
    const horaActualElemento = document.getElementById('hora-actual');

    // Función para obtener la hora actual en formato HH:mm:ss
    function obtenerHoraActual() {
      const fecha = new Date();
      const horas = fecha.getHours().toString().padStart(2, '0');
      const minutos = fecha.getMinutes().toString().padStart(2, '0');
      const segundos = fecha.getSeconds().toString().padStart(2, '0');
      return `${horas}:${minutos}:${segundos}`;
    }

    // Función para actualizar la hora actual cada segundo
    function actualizarHora() {
      horaActualElemento.textContent = obtenerHoraActual();
    }

    // Actualizar la hora actual inicialmente y luego cada segundo
    actualizarHora();
    setInterval(actualizarHora, 1000);
  </script>
</body>
</html>
