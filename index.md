<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Railway to Hell | A Hellish Metroidvania Adventure</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Kanit:wght@300;400;600&display=swap" rel="stylesheet">
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
      padding-top: 60px;
      font-family: 'Kanit', sans-serif;
      color: #e0e0e0;
      min-height: 100vh;
    }
    
    h1, h2, h3, h4 {
      font-family: 'Orbitron', sans-serif;
      text-transform: uppercase;
      letter-spacing: 1px;
    }
    
    .container {
      max-width: 1200px;
    }
    
    .hero {
      text-align: center;
      padding: 60px 20px;
      background: 
        linear-gradient(135deg, rgba(138, 3, 3, 0.8) 0%, rgba(10, 10, 10, 0.9) 70%),
        url('assets/train-texture.jpg');
      background-size: cover;
      color: white;
      border-radius: 15px;
      border: 2px solid var(--hell-red);
      box-shadow: 0 0 30px rgba(255, 30, 30, 0.4);
      margin-bottom: 40px;
      position: relative;
      overflow: hidden;
    }
    
    .hero::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 5px;
      background: linear-gradient(90deg, 
        var(--hell-red), 
        var(--hell-orange), 
        var(--neon-yellow),
        var(--hell-orange),
        var(--hell-red));
    }
    
    .titulo-imagen {
      max-width: 80%;
      height: auto;
      margin-bottom: 30px;
      filter: drop-shadow(0 0 15px #ff1e56);
      transition: transform 0.3s ease;
    }
    
    .titulo-imagen:hover {
      transform: scale(1.03);
    }
    
    .lead {
      font-size: 1.25rem;
      line-height: 1.6;
      max-width: 800px;
      margin: 0 auto;
      text-shadow: 0 0 10px rgba(0,0,0,0.8);
    }
    
    .section {
      background-color: rgba(34, 34, 34, 0.8);
      padding: 30px;
      margin-bottom: 40px;
      border-radius: 10px;
      border-left: 4px solid var(--hell-red);
      box-shadow: 0 5px 15px rgba(0,0,0,0.3);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    
    .section:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 25px rgba(255, 30, 30, 0.2);
    }
    
    h2 {
      color: var(--hell-orange);
      border-bottom: 2px solid var(--hell-red);
      padding-bottom: 10px;
      margin-bottom: 20px;
      position: relative;
    }
    
    h2::after {
      content: "";
      position: absolute;
      bottom: -2px;
      left: 0;
      width: 100px;
      height: 2px;
      background: var(--neon-yellow);
    }
    
    ul {
      list-style-type: none;
      padding-left: 0;
    }
    
    ul li {
      margin-bottom: 10px;
      padding-left: 25px;
      position: relative;
    }
    
    ul li::before {
      content: "➤";
      position: absolute;
      left: 0;
      color: var(--hell-red);
    }
    
    .controls-list code {
      background: rgba(255, 107, 30, 0.2);
      color: var(--neon-yellow);
      padding: 3px 8px;
      border-radius: 4px;
      border: 1px solid var(--hell-orange);
      font-family: monospace;
    }
    
    .gallery img {
      margin-bottom: 20px;
      border-radius: 8px;
      border: 2px solid var(--railway-gray);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    
    .gallery img:hover {
      transform: scale(1.02);
      box-shadow: 0 0 20px rgba(255, 30, 30, 0.6);
      border-color: var(--hell-red);
    }
    
    .blockquote {
      border-left: 4px solid var(--hell-red);
      padding-left: 20px;
      font-style: italic;
      color: #ccc;
      margin: 30px 0;
    }
    
    .blockquote-footer {
      color: var(--hell-orange);
    }
    
    footer {
      text-align: center;
      padding: 30px;
      margin-top: 60px;
      background: linear-gradient(to right, var(--blood-red), var(--railway-gray));
      border-radius: 10px;
      color: white;
      border-top: 2px solid var(--hell-red);
    }
    
    footer p {
      margin-bottom: 0;
      font-size: 0.9rem;
    }
    
    .roles-list {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 20px;
    }
    
    .role-card {
      background: rgba(34, 34, 34, 0.7);
      padding: 15px;
      border-radius: 8px;
      border-left: 3px solid var(--hell-red);
      transition: all 0.3s ease;
    }
    
    .role-card:hover {
      background: rgba(50, 50, 50, 0.7);
      transform: translateY(-3px);
    }
    
    .trailer-placeholder {
      background: rgba(20, 20, 20, 0.7);
      height: 400px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 10px;
      border: 2px dashed var(--hell-red);
      color: var(--hell-orange);
      font-size: 1.2rem;
    }
    
    .nav-tabs .nav-link {
      color: #ccc;
      border: none;
      padding: 10px 20px;
    }
    
    .nav-tabs .nav-link.active {
      color: var(--hell-red);
      background: transparent;
      border-bottom: 3px solid var(--hell-red);
    }
    
    .tab-content {
      padding: 20px;
      background: rgba(34, 34, 34, 0.7);
      border-radius: 0 0 10px 10px;
    }
    
    @media (max-width: 768px) {
      .hero {
        padding: 40px 15px;
      }
      
      .titulo-imagen {
        max-width: 100%;
      }
      
      .section {
        padding: 20px;
      }
    }
    
    /* Animated elements */
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
    
    /* Train track divider */
    .track-divider {
      height: 40px;
      background: 
        linear-gradient(90deg, 
          transparent 0%, 
          #333 10%, 
          #333 15%, 
          #fff 15.5%, 
          #fff 16.5%, 
          #333 17%, 
          #333 22%, 
          transparent 100%);
      background-size: 40px 100%;
      margin: 40px 0;
      position: relative;
    }
    
    .track-divider::before {
      content: "";
      position: absolute;
      top: 18px;
      left: 0;
      right: 0;
      height: 4px;
      background: linear-gradient(90deg, 
        transparent, 
        var(--hell-red), 
        var(--hell-orange), 
        var(--hell-red), 
        transparent);
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="hero">
      <img src="assets/titulo.png" alt="Railway to Hell" class="img-fluid titulo-imagen flicker">
      <p class="lead">Railway to Hell is a Metroidvania action and exploration video game set in a hellish version of a railway system. The player controls Nadia, a girl from a gang trapped in this hell, seeking redemption and the chance to escape with her deceased sister. Through intense melee combat, distance combat, progressive skill upgrades and exploration of the train lines, you must challenge the demonic lords who control this hellish system.</p>
    </div>

    <div class="track-divider"></div>

    <div class="section">
      <h2><i class="fas fa-film"></i> Trailer</h2>
      <div class="trailer-placeholder">
        [Embed YouTube trailer here]
      </div>
      <blockquote class="blockquote mt-4">
        "Death is not the last stop"
        <footer class="blockquote-footer">Railway to Hell</footer>
      </blockquote>
    </div>

    <div class="section">
      <h2><i class="fas fa-book"></i> Narrative</h2>
      <p>
        Nadia finds herself in a hellish railway system where demonic lords control different lines. Guided by what she believes are her sister's memories, she must battle through the system, uncovering dark truths about her past and the nature of this underworld.
      </p>
      <p>
        The railway lines represent different circles of hell, each with unique environments and challenges. From the industrial wasteland of Line 666 to the cathedral-like stations of the Crimson Express, each area tells part of Nadia's tragic story.
      </p>
    </div>

    <div class="section">
      <h2><i class="fas fa-bullseye"></i> Game Objective</h2>
      <ul>
        <li>Explore interconnected tunnels and stations filled with secrets</li>
        <li>Defeat demonic bosses to gain new mobility abilities</li>
        <li>Solve environmental puzzles using your growing arsenal</li>
        <li>Uncover the truth about your sister and this hellish world</li>
        <li>Upgrade your weapons and abilities to access new areas</li>
        <li>Survive the ever-changing train schedules that alter the environment</li>
      </ul>
    </div>

    <div class="track-divider"></div>

    <div class="section">
      <h2><i class="fas fa-palette"></i> Art Style & Inspirations</h2>
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
      <h2><i class="fas fa-gamepad"></i> Controls</h2>
      
      <ul class="nav nav-tabs" id="controlsTab" role="tablist">
        <li class="nav-item" role="presentation">
          <button class="nav-link active" id="controller-tab" data-bs-toggle="tab" data-bs-target="#controller" type="button" role="tab">Controller</button>
        </li>
        <li class="nav-item" role="presentation">
          <button class="nav-link" id="keyboard-tab" data-bs-toggle="tab" data-bs-target="#keyboard" type="button" role="tab">Keyboard</button>
        </li>
      </ul>
      
      <div class="tab-content" id="controlsTabContent">
        <div class="tab-pane fade show active" id="controller" role="tabpanel">
          <div class="row">
            <div class="col-md-6">
              <h4>Movement</h4>
              <ul>
                <li><code>Left Stick</code>: Move</li>
                <li><code>X / A</code>: Jump</li>
                <li><code>R1 / RB</code>: Dash</li>
              </ul>
            </div>
            <div class="col-md-6">
              <h4>Combat</h4>
              <ul>
                <li><code>Square / X</code>: Melee Attack</li>
                <li><code>R2 / RT</code>: Use whip</li>
                <li><code>L2 / LT</code>: Throw Balls</li>
              </ul>
            </div>
          </div>
          <div class="row mt-3">
            <div class="col-md-6">
              <h4>Interaction</h4>
              <ul>
                <li><code>Circle / B</code>: Use Key (Doors/Interactions)</li>
                <li><code>Circle / B</code>: Close dialogues</li>
                <li><code>Circle / B</code>: Use checkpoints</li>
              </ul>
            </div>
            <div class="col-md-6">
              <h4>System</h4>
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
              <h4>Movement</h4>
              <ul>
                <li><code>A/D</code>: Move Left/Right</li>
                <li><code>SPACE</code>: Jump</li>
                <li><code>SHIFT</code>: Dash</li>
              </ul>
            </div>
            <div class="col-md-6">
              <h4>Combat</h4>
              <ul>
                <li><code>J</code>: Melee Attack</li>
                <li><code>K</code>: Use whip</li>
                <li><code>L</code>: Throw Balls</li>
              </ul>
            </div>
          </div>
          <div class="row mt-3">
            <div class="col-md-6">
              <h4>Interaction</h4>
              <ul>
                <li><code>E</code>: Use Key (Doors/Interactions)</li>
                <li><code>E</code>: Close dialogues</li>
                <li><code>E</code>: Use checkpoints</li>
              </ul>
            </div>
            <div class="col-md-6">
              <h4>System</h4>
              <ul>
                <li><code>M</code>: Map</li>
                <li><code>ESC</code>: Pause</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="track-divider"></div>

    <div class="section">
      <h2><i class="fas fa-users"></i> Development Team</h2>
      <div class="roles-list">
        <div class="role-card">
          <h5>Sanchez Carraro Felipe</h5>
          <p class="text-muted">Lead Programmer</p>
        </div>
        <div class="role-card">
          <h5>Sanjose Aragon Pablo</h5>
          <p class="text-muted">Game Designer</p>
        </div>
        <div class="role-card">
          <h5>Sarrias Basurte Martina</h5>
          <p class="text-muted">Art Director</p>
        </div>
        <div class="role-card">
          <h5>Vida Bosch Javier</h5>
          <p class="text-muted">Level Designer</p>
        </div>
      </div>
    </div>

    <div class="section">
      <h2><i class="fas fa-images"></i> Gallery</h2>
      <div class="row gallery">
        <div class="col-md-4">
          <img src="assets/imagen1.jpg" class="img-fluid rounded shadow" alt="Gameplay Screenshot 1">
        </div>
        <div class="col-md-4">
          <img src="assets/imagen2.jpg" class="img-fluid rounded shadow" alt="Gameplay Screenshot 2">
        </div>
        <div class="col-md-4">
          <img src="assets/imagen3.jpg" class="img-fluid rounded shadow" alt="Gameplay Screenshot 3">
        </div>
        <div class="col-md-6 mt-4">
          <img src="assets/imagen4.jpg" class="img-fluid rounded shadow" alt="Boss Design">
        </div>
        <div class="col-md-6 mt-4">
          <img src="assets/imagen5.jpg" class="img-fluid rounded shadow" alt="Environment Concept">
        </div>
      </div>
    </div>

    <div class="section">
      <h2><i class="fas fa-link"></i> Links</h2>
      <div class="d-flex flex-wrap gap-3">
        <a href="#" class="btn btn-outline-danger">Steam Page</a>
        <a href="#" class="btn btn-outline-warning">Press Kit</a>
        <a href="#" class="btn btn-outline-info">Developer Blog</a>
        <a href="#" class="btn btn-outline-secondary">Support</a>
      </div>
    </div>

    <footer class="flicker">
      <p>© 2025 Railway to Hell. All rights reserved. | "Death is not the last stop"</p>
    </footer>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
</body>
</html>