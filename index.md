<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Railway to Hell | LastStop Studios</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --hell-red: #ff1e1e;
      --hell-orange: #ff6b1e;
      --dark-bg: #0a0a0a;
      --railway-gray: #222222;
      --neon-yellow: #f5f749;
      --blood-red: #8a0303;
    }
    
    body {
      background-color: var(--dark-bg);
      background-image: 
        linear-gradient(rgba(255, 30, 30, 0.05) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255, 30, 30, 0.05) 1px, transparent 1px);
      background-size: 40px 40px;
      padding-top: 0;
      font-family: 'Orbitron', sans-serif;
      color: #e0e0e0;
      min-height: 100vh;
    }
    
    .studio-header {
      font-family: 'Press Start 2P', cursive;
      color: var(--neon-yellow);
      text-shadow: 0 0 10px var(--hell-red);
      text-align: center;
      padding: 20px 0;
      font-size: 1.2rem;
      border-bottom: 3px solid var(--hell-red);
    }
    
    .game-title {
      font-family: 'Press Start 2P', cursive;
      font-size: 3rem;
      color: white;
      text-shadow: 0 0 10px var(--hell-red);
      text-align: center;
      margin: 30px 0;
    }
    
    .tagline {
      font-family: 'Press Start 2P', cursive;
      font-size: 1.2rem;
      color: var(--neon-yellow);
      text-align: center;
      margin-bottom: 40px;
    }
    
    .container {
      max-width: 1200px;
      padding-bottom: 60px;
    }
    
    .section {
      background-color: rgba(34, 34, 34, 0.9);
      padding: 30px;
      margin-bottom: 40px;
      border-radius: 5px;
      border-left: 6px solid var(--hell-red);
      box-shadow: 0 5px 15px rgba(0,0,0,0.5);
      position: relative;
      overflow: hidden;
    }
    
    .section::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 3px;
      background: linear-gradient(90deg, 
        transparent, 
        var(--hell-red), 
        var(--hell-orange), 
        var(--hell-red), 
        transparent);
    }
    
    h2 {
      font-family: 'Press Start 2P', cursive;
      color: var(--hell-orange);
      font-size: 1.5rem;
      margin-bottom: 25px;
      position: relative;
      padding-bottom: 10px;
    }
    
    h2::after {
      content: "";
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100px;
      height: 3px;
      background: var(--neon-yellow);
    }
    
    .lead {
      font-size: 1.1rem;
      line-height: 1.7;
    }
    
    ul {
      list-style-type: none;
      padding-left: 0;
    }
    
    ul li {
      margin-bottom: 10px;
      padding-left: 25px;
      position: relative;
      font-size: 0.9rem;
    }
    
    ul li::before {
      content: ">";
      position: absolute;
      left: 0;
      color: var(--hell-red);
      font-weight: bold;
    }
    
    .controls-list code {
      background: rgba(255, 107, 30, 0.2);
      color: var(--neon-yellow);
      padding: 2px 6px;
      border-radius: 3px;
      border: 1px solid var(--hell-orange);
      font-family: monospace;
      font-size: 0.8rem;
    }
    
    .gallery img {
      margin-bottom: 20px;
      border-radius: 5px;
      border: 2px solid var(--railway-gray);
      transition: all 0.3s ease;
    }
    
    .gallery img:hover {
      transform: scale(1.02);
      box-shadow: 0 0 15px rgba(255, 30, 30, 0.6);
      border-color: var(--hell-red);
    }
    
    .blockquote {
      border-left: 4px solid var(--hell-red);
      padding-left: 20px;
      font-style: italic;
      color: #ccc;
      margin: 25px 0;
    }
    
    .blockquote-footer {
      color: var(--hell-orange);
      font-size: 0.8rem;
    }
    
    footer {
      text-align: center;
      padding: 30px;
      margin-top: 60px;
      background: linear-gradient(to right, var(--blood-red), var(--railway-gray));
      border-top: 3px solid var(--hell-red);
      font-family: 'Press Start 2P', cursive;
      font-size: 0.8rem;
    }
    
    .roles-list {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 20px;
    }
    
    .role-card {
      background: rgba(40, 40, 40, 0.9);
      padding: 15px;
      border-radius: 5px;
      border-left: 3px solid var(--hell-red);
      transition: all 0.3s ease;
    }
    
    .role-card h5 {
      color: var(--neon-yellow);
      font-family: 'Press Start 2P', cursive;
      font-size: 0.9rem;
    }
    
    .role-card p {
      color: #ffffff;
      font-size: 0.8rem;
    }
    
    .role-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 5px 15px rgba(255, 30, 30, 0.4);
      border-left-color: var(--neon-yellow);
    }
    
    .trailer-placeholder {
      background: rgba(20, 20, 20, 0.7);
      height: 400px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 5px;
      border: 2px dashed var(--hell-red);
      color: var(--hell-orange);
      font-family: 'Press Start 2P', cursive;
      font-size: 1rem;
    }
    
    .nav-tabs .nav-link {
      color: #ccc;
      border: none;
      padding: 10px 15px;
      font-family: 'Press Start 2P', cursive;
      font-size: 0.7rem;
    }
    
    .nav-tabs .nav-link.active {
      color: var(--hell-red);
      background: transparent;
      border-bottom: 3px solid var(--hell-red);
    }
    
    .tab-content {
      padding: 20px;
      background: rgba(34, 34, 34, 0.7);
      border-radius: 0 0 5px 5px;
    }
    
    .btn-outline-danger {
      font-family: 'Press Start 2P', cursive;
      font-size: 0.7rem;
    }
    
    /* Efectos especiales */
    @keyframes flicker {
      0%, 19%, 21%, 23%, 25%, 54%, 56%, 100% {
        opacity: 1;
      }
      20%, 22%, 24%, 55% {
        opacity: 0.5;
      }
    }
    
    .flicker {
      animation: flicker 3s infinite;
    }
    
    .pixel-border {
      position: fixed;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      background: 
        linear-gradient(to right, var(--hell-red) 0%, transparent 1px, transparent calc(100% - 1px), var(--hell-red) 100%),
        linear-gradient(to bottom, var(--hell-red) 0%, transparent 1px, transparent calc(100% - 1px), var(--hell-red) 100%);
      background-size: 20px 20px;
      pointer-events: none;
      z-index: 1000;
      opacity: 0.3;
    }
    
    @media (max-width: 768px) {
      .game-title {
        font-size: 2rem;
      }
      
      .tagline {
        font-size: 0.9rem;
      }
      
      h2 {
        font-size: 1.2rem;
      }
      
      .section {
        padding: 20px;
      }
    }
  </style>
</head>
<body>
  <div class="pixel-border"></div>
  
  <div class="studio-header flicker">LAST STOP STUDIOS</div>
  
  <div class="container">
    <div class="text-center">
      <h1 class="game-title">RAILWAY TO HELL</h1>
      <p class="tagline">"La mort no és l'última parada"</p>
    </div>

    <div class="section">
      <h2>TRAILER</h2>
      <div class="trailer-placeholder">
        [EMBED YOUTUBE TRAILER HERE]
      </div>
      <blockquote class="blockquote mt-4">
        "Death is not the last stop"
        <footer class="blockquote-footer">Railway to Hell</footer>
      </blockquote>
    </div>

    <div class="section">
      <h2>NARRATIVE</h2>
      <p class="lead">
        Nadia finds herself in a hellish railway system where demonic lords control different lines. Guided by what she believes are her sister's memories, she must battle through the system, uncovering dark truths about her past and the nature of this underworld.
      </p>
      <p>
        The railway lines represent different circles of hell, each with unique environments and challenges. From the industrial wasteland of Line 666 to the cathedral-like stations of the Crimson Express, each area tells part of Nadia's tragic story.
      </p>
    </div>

    <div class="section">
      <h2>GAME OBJECTIVE</h2>
      <ul>
        <li>Explore interconnected tunnels and stations filled with secrets</li>
        <li>Defeat demonic bosses to gain new mobility abilities</li>
        <li>Solve environmental puzzles using your growing arsenal</li>
        <li>Uncover the truth about your sister and this hellish world</li>
        <li>Upgrade your weapons and abilities to access new areas</li>
        <li>Survive the ever-changing train schedules that alter the environment</li>
      </ul>
    </div>

    <div class="section">
      <h2>ART STYLE & INSPIRATIONS</h2>
      <p>Our pixel-art aesthetic combines gritty urban decay with supernatural elements, inspired by:</p>
      <ul>
        <li>Classic Metroidvania games with modern fluid animations</li>
        <li>Underground graffiti culture and urban exploration</li>
        <li>Gothic and demonic mythology reimagined in a railway setting</li>
        <li>Barcelona's unique architecture (like Gaudí's mosaics) twisted into hellscapes</li>
        <li>Industrial decay and abandoned subway systems</li>
      </ul>
    </div>

    <div class="section">
      <h2>CONTROLS</h2>
      
      <ul class="nav nav-tabs" id="controlsTab" role="tablist">
        <li class="nav-item" role="presentation">
          <button class="nav-link active" id="controller-tab" data-bs-toggle="tab" data-bs-target="#controller" type="button" role="tab">CONTROLLER</button>
        </li>
        <li class="nav-item" role="presentation">
          <button class="nav-link" id="keyboard-tab" data-bs-toggle="tab" data-bs-target="#keyboard" type="button" role="tab">KEYBOARD</button>
        </li>
      </ul>
      
      <div class="tab-content" id="controlsTabContent">
        <div class="tab-pane fade show active" id="controller" role="tabpanel">
          <div class="row">
            <div class="col-md-6">
              <h4>MOVEMENT</h4>
              <ul>
                <li><code>Left Stick</code>: Move</li>
                <li><code>X / A</code>: Jump</li>
                <li><code>R1 / RB</code>: Dash</li>
              </ul>
            </div>
            <div class="col-md-6">
              <h4>COMBAT</h4>
              <ul>
                <li><code>Square / X</code>: Melee Attack</li>
                <li><code>R2 / RT</code>: Use whip</li>
                <li><code>L2 / LT</code>: Throw Balls</li>
              </ul>
            </div>
          </div>
          <div class="row mt-3">
            <div class="col-md-6">
              <h4>INTERACTION</h4>
              <ul>
                <li><code>Circle / B</code>: Use Key (Doors/Interactions)</li>
                <li><code>Circle / B</code>: Close dialogues</li>
                <li><code>Circle / B</code>: Use checkpoints</li>
              </ul>
            </div>
            <div class="col-md-6">
              <h4>SYSTEM</h4>
              <ul>
                <li><code>Triangle / Y</code>: Map</li>
                <li><code>Options / Menu</code>: Pause</li>
              </ul>
            </div>
          </div>
        </div>
        
        <div class="tab-pane fade" id="keyboard" role="tabpanel">
          <div class="row">
            <div class="col-md-6">
              <h4>MOVEMENT</h4>
              <ul>
                <li><code>A/D</code>: Move Left/Right</li>
                <li><code>SPACE</code>: Jump</li>
                <li><code>SHIFT</code>: Dash</li>
              </ul>
            </div>
            <div class="col-md-6">
              <h4>COMBAT</h4>
              <ul>
                <li><code>J</code>: Melee Attack</li>
                <li><code>K</code>: Use whip</li>
                <li><code>L</code>: Throw Balls</li>
              </ul>
            </div>
          </div>
          <div class="row mt-3">
            <div class="col-md-6">
              <h4>INTERACTION</h4>
              <ul>
                <li><code>E</code>: Use Key (Doors/Interactions)</li>
                <li><code>E</code>: Close dialogues</li>
                <li><code>E</code>: Use checkpoints</li>
              </ul>
            </div>
            <div class="col-md-6">
              <h4>SYSTEM</h4>
              <ul>
                <li><code>M</code>: Map</li>
                <li><code>ESC</code>: Pause</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="section">
      <h2>DEVELOPMENT TEAM</h2>
      <div class="roles-list">
        <div class="role-card">
          <h5>SANCHEZ CARRARO FELIPE</h5>
          <p>Lead Programmer</p>
        </div>
        <div class="role-card">
          <h5>SANJOSE ARAGON PABLO</h5>
          <p>Game Designer</p>
        </div>
        <div class="role-card">
          <h5>SARRIAS BASURTE MARTINA</h5>
          <p>Art Director</p>
        </div>
        <div class="role-card">
          <h5>VIDA BOSCH JAVIER</h5>
          <p>Level Designer</p>
        </div>
      </div>
    </div>

    <div class="section">
      <h2>GALLERY</h2>
      <div class="row gallery">
        <div class="col-md-4">
          <img src="assets/imagen1.jpg" class="img-fluid rounded" alt="Gameplay Screenshot 1">
        </div>
        <div class="col-md-4">
          <img src="assets/imagen2.jpg" class="img-fluid rounded" alt="Gameplay Screenshot 2">
        </div>
        <div class="col-md-4">
          <img src="assets/imagen3.jpg" class="img-fluid rounded" alt="Gameplay Screenshot 3">
        </div>
      </div>
    </div>

    <div class="section">
      <h2>LINKS</h2>
      <div class="d-flex flex-wrap gap-3 justify-content-center">
        <a href="#" class="btn btn-outline-danger">STEAM PAGE</a>
        <a href="#" class="btn btn-outline-danger">PRESS KIT</a>
        <a href="#" class="btn btn-outline-danger">DEVELOPER BLOG</a>
      </div>
    </div>
  </div>

  <footer class="flicker">
    <p>© 2025 RAILWAY TO HELL. ALL RIGHTS RESERVED.</p>
    <p>"DEATH IS NOT THE LAST STOP"</p>
    <p>LAST STOP STUDIOS - GRUP4</p>
  </footer>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>