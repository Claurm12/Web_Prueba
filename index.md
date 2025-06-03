<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Railway to Hell | LastStop Studios</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Silkscreen&display=swap" rel="stylesheet">
  <style>
    :root {
      --hell-main: #8a0303;    /* Rojo sangre principal */
      --hell-accent: #ff6b1e;  /* Naranja infernal */
      --hell-dark: #1a0000;    /* Fondo oscuro */
      --hell-light: #f5f749;   /* Amarillo neón */
      --pixel-border: #3a0c0c; /* Borde pixelado */
    }
    
    body {
      background-color: var(--hell-dark);
      background-image: 
        url('assets/pixel-grid.png');
      font-family: 'Silkscreen', cursive;
      color: #e0e0e0;
      line-height: 1.6;
      padding: 0;
      margin: 0;
      image-rendering: pixelated;
      image-rendering: -moz-crisp-edges;
      image-rendering: crisp-edges;
    }
    
    .pixel-container {
      max-width: 1200px;
      margin: 20px auto;
      border: 4px solid var(--hell-main);
      background-color: rgba(26, 0, 0, 0.85);
      box-shadow: 0 0 0 8px var(--hell-accent),
                  0 0 30px rgba(255, 30, 30, 0.6);
      position: relative;
      overflow: hidden;
    }
    
    .pixel-container::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 5px;
      background: linear-gradient(90deg, 
        var(--hell-main), 
        var(--hell-accent), 
        var(--hell-light),
        var(--hell-accent),
        var(--hell-main));
    }
    
    .pixel-header {
      padding: 30px;
      text-align: center;
      background: url('assets/train-pixel-bg.png') center/cover;
      border-bottom: 4px solid var(--hell-main);
      position: relative;
    }
    
    .game-title {
      font-family: 'Press Start 2P', cursive;
      font-size: 3rem;
      color: var(--hell-light);
      text-shadow: 4px 4px 0 var(--hell-main),
                  8px 8px 0 #000;
      margin: 0;
      padding: 20px;
      background-color: rgba(26, 0, 0, 0.7);
      display: inline-block;
      border: 4px solid var(--hell-accent);
    }
    
    .game-tagline {
      font-family: 'Press Start 2P', cursive;
      font-size: 1rem;
      color: var(--hell-accent);
      margin-top: 20px;
      display: inline-block;
      background-color: rgba(26, 0, 0, 0.9);
      padding: 10px 20px;
      border: 3px solid var(--hell-light);
    }
    
    .pixel-section {
      padding: 30px;
      border-bottom: 2px dashed var(--hell-accent);
      position: relative;
    }
    
    .pixel-section:last-child {
      border-bottom: none;
    }
    
    .section-title {
      font-family: 'Press Start 2P', cursive;
      font-size: 1.5rem;
      color: var(--hell-light);
      margin-bottom: 25px;
      padding-bottom: 10px;
      border-bottom: 3px solid var(--hell-accent);
      position: relative;
    }
    
    .section-title::after {
      content: "";
      position: absolute;
      bottom: -6px;
      left: 0;
      width: 100px;
      height: 3px;
      background: var(--hell-light);
    }
    
    .pixel-text {
      font-size: 0.9rem;
      margin-bottom: 20px;
    }
    
    .pixel-list {
      list-style-type: none;
      padding-left: 0;
    }
    
    .pixel-list li {
      margin-bottom: 10px;
      padding-left: 25px;
      position: relative;
      font-size: 0.9rem;
    }
    
    .pixel-list li::before {
      content: ">";
      position: absolute;
      left: 0;
      color: var(--hell-accent);
      font-weight: bold;
    }
    
    .pixel-img {
      image-rendering: pixelated;
      border: 4px solid var(--hell-main);
      margin-bottom: 20px;
      transition: all 0.3s ease;
      box-shadow: 0 0 15px rgba(255, 30, 30, 0.4);
    }
    
    .pixel-img:hover {
      transform: scale(1.05);
      border-color: var(--hell-light);
      box-shadow: 0 0 25px rgba(245, 247, 73, 0.6);
    }
    
    .pixel-btn {
      font-family: 'Press Start 2P', cursive;
      font-size: 0.8rem;
      padding: 10px 20px;
      background-color: var(--hell-main);
      color: white;
      border: 3px solid var(--hell-light);
      text-transform: uppercase;
      transition: all 0.3s ease;
      margin: 5px;
      display: inline-block;
    }
    
    .pixel-btn:hover {
      background-color: var(--hell-accent);
      color: #000;
      transform: translateY(-3px);
      box-shadow: 0 5px 0 var(--hell-light);
    }
    
    .role-card {
      background-color: rgba(138, 3, 3, 0.3);
      border: 3px solid var(--hell-main);
      padding: 15px;
      margin-bottom: 20px;
      transition: all 0.3s ease;
    }
    
    .role-card:hover {
      background-color: rgba(138, 3, 3, 0.5);
      border-color: var(--hell-light);
      transform: translateY(-5px);
    }
    
    .role-name {
      font-family: 'Press Start 2P', cursive;
      font-size: 1rem;
      color: var(--hell-light);
      margin-bottom: 5px;
    }
    
    .pixel-footer {
      background: linear-gradient(to right, var(--hell-main), var(--hell-dark));
      padding: 20px;
      text-align: center;
      font-family: 'Press Start 2P', cursive;
      font-size: 0.7rem;
      border-top: 4px solid var(--hell-accent);
    }
    
    /* Efecto de pixelado */
    .pixel-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-image: 
        linear-gradient(to right, rgba(0,0,0,0.05) 1px, transparent 1px),
        linear-gradient(to bottom, rgba(0,0,0,0.05) 1px, transparent 1px);
      background-size: 4px 4px;
      pointer-events: none;
      z-index: 1000;
    }
    
    @media (max-width: 768px) {
      .game-title {
        font-size: 2rem;
      }
      
      .game-tagline {
        font-size: 0.7rem;
      }
      
      .section-title {
        font-size: 1.2rem;
      }
    }
  </style>
</head>
<body>
  <div class="pixel-overlay"></div>
  
  <div class="pixel-container">
    <!-- Header -->
    <div class="pixel-header">
      <h1 class="game-title">RAILWAY TO HELL</h1>
      <p class="game-tagline">"La mort no és l'última parada"</p>
    </div>
    
    <!-- Trailer Section -->
    <div class="pixel-section">
      <h2 class="section-title">TRAILER</h2>
      <div class="ratio ratio-16x9">
        <iframe src="https://www.youtube.com/embed/YOUR_VIDEO_ID" allowfullscreen></iframe>
      </div>
      <p class="pixel-text text-center mt-3">"Death is not the last stop"</p>
    </div>
    
    <!-- Narrative Section -->
    <div class="pixel-section">
      <h2 class="section-title">NARRATIVA</h2>
      <p class="pixel-text">Nadia se encuentra en un sistema ferroviario infernal donde señores demoníacos controlan diferentes líneas. Guiada por lo que cree que son los recuerdos de su hermana, debe luchar a través del sistema, descubriendo oscuras verdades sobre su pasado y la naturaleza de este inframundo.</p>
      <p class="pixel-text">Las líneas de tren representan diferentes círculos del infierno, cada una con entornos y desafíos únicos. Desde el páramo industrial de la Línea 666 hasta las estaciones catedralicias del Expreso Carmesí, cada área cuenta parte de la trágica historia de Nadia.</p>
    </div>
    
    <!-- Game Objective -->
    <div class="pixel-section">
      <h2 class="section-title">OBJETIVO DEL JUEGO</h2>
      <ul class="pixel-list">
        <li>Explora túneles y estaciones interconectadas llenas de secretos</li>
        <li>Derrota a jefes demoníacos para ganar nuevas habilidades de movilidad</li>
        <li>Resuelve puzles ambientales usando tu arsenal en crecimiento</li>
        <li>Descubre la verdad sobre tu hermana y este mundo infernal</li>
        <li>Mejora tus armas y habilidades para acceder a nuevas áreas</li>
      </ul>
    </div>
    
    <!-- Art Style -->
    <div class="pixel-section">
      <h2 class="section-title">ESTILO ARTÍSTICO</h2>
      <div class="row">
        <div class="col-md-6">
          <img src="assets/art-style-1.png" class="img-fluid pixel-img" alt="Estilo de arte pixelado">
        </div>
        <div class="col-md-6">
          <img src="assets/art-style-2.png" class="img-fluid pixel-img" alt="Personajes pixelados">
        </div>
      </div>
      <p class="pixel-text">Nuestra estética pixel-art combina la decadencia urbana con elementos sobrenaturales, inspirada en:</p>
      <ul class="pixel-list">
        <li>Juegos Metroidvania clásicos con animaciones fluidas modernas</li>
        <li>Cultura del graffiti subterráneo y exploración urbana</li>
        <li>Mitología gótica y demoníaca reimaginada en un entorno ferroviario</li>
        <li>Arquitectura única de Barcelona retorcida en paisajes infernales</li>
      </ul>
    </div>
    
    <!-- Controls -->
    <div class="pixel-section">
      <h2 class="section-title">CONTROLES</h2>
      <div class="row">
        <div class="col-md-6">
          <h3 class="pixel-text" style="color: var(--hell-light);">MANDO</h3>
          <ul class="pixel-list">
            <li><strong>Stick Izquierdo:</strong> Movimiento</li>
            <li><strong>X/A:</strong> Saltar</li>
            <li><strong>R1/RB:</strong> Dash</li>
            <li><strong>Cuadrado/X:</strong> Ataque cuerpo a cuerpo</li>
          </ul>
        </div>
        <div class="col-md-6">
          <h3 class="pixel-text" style="color: var(--hell-light);">TECLADO</h3>
          <ul class="pixel-list">
            <li><strong>A/D:</strong> Moverse izquierda/derecha</li>
            <li><strong>ESPACIO:</strong> Saltar</li>
            <li><strong>SHIFT:</strong> Dash</li>
            <li><strong>J:</strong> Ataque cuerpo a cuerpo</li>
          </ul>
        </div>
      </div>
    </div>
    
    <!-- Team -->
    <div class="pixel-section">
      <h2 class="section-title">EQUIPO</h2>
      <div class="row">
        <div class="col-md-3">
          <div class="role-card">
            <h3 class="role-name">FELIPE</h3>
            <p class="pixel-text">Programador Principal</p>
          </div>
        </div>
        <div class="col-md-3">
          <div class="role-card">
            <h3 class="role-name">PABLO</h3>
            <p class="pixel-text">Diseñador de Juego</p>
          </div>
        </div>
        <div class="col-md-3">
          <div class="role-card">
            <h3 class="role-name">MARTINA</h3>
            <p class="pixel-text">Directora de Arte</p>
          </div>
        </div>
        <div class="col-md-3">
          <div class="role-card">
            <h3 class="role-name">JAVIER</h3>
            <p class="pixel-text">Diseñador de Niveles</p>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Gallery -->
    <div class="pixel-section">
      <h2 class="section-title">GALERÍA</h2>
      <div class="row">
        <div class="col-md-4">
          <img src="assets/gallery-1.png" class="img-fluid pixel-img" alt="Captura de pantalla 1">
        </div>
        <div class="col-md-4">
          <img src="assets/gallery-2.png" class="img-fluid pixel-img" alt="Captura de pantalla 2">
        </div>
        <div class="col-md-4">
          <img src="assets/gallery-3.png" class="img-fluid pixel-img" alt="Captura de pantalla 3">
        </div>
      </div>
    </div>
    
    <!-- Links -->
    <div class="pixel-section text-center">
      <h2 class="section-title">ENLACES</h2>
      <a href="#" class="pixel-btn">PÁGINA DE STEAM</a>
      <a href="#" class="pixel-btn">KIT DE PRENSA</a>
      <a href="#" class="pixel-btn">BLOG DEL DESARROLLO</a>
    </div>
    
    <!-- Footer -->
    <div class="pixel-footer">
      <p>© 2025 RAILWAY TO HELL - LAST STOP STUDIOS</p>
      <p>"DEATH IS NOT THE LAST STOP"</p>
    </div>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>