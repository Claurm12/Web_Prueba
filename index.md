
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Mi Página Bonita</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
  <style>
    body {
      background: #ffffff;
      padding-top: 60px;
    }
    .hero {
      text-align: center;
      padding: 60px 20px;
      background: #ff0000;
      color: white;
      border-radius: 15px;
    }
    .hero h1 {
      font-size: 3rem;
    }
    .hero p {
      font-size: 1.2rem;
    }
    footer {
      text-align: center;
      padding: 20px;
      margin-top: 60px;
      background: #eee;
      border-radius: 10px;
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="hero">
      <h1>Bienvenido a mi web</h1>
      <p>Pagina de prueba</p>
    </div>

    <div class="mt-5">
      <h2>Galería de imágenes</h2>
      <div class="row">
        <div class="col-md-4">
          <img src="assets/imagen1.jpg" class="img-fluid rounded shadow" alt="Imagen 1">
        </div>
        <div class="col-md-4">
          <img src="assets/imagen2.jpg" class="img-fluid rounded shadow" alt="Imagen 2">
        </div>
        <div class="col-md-4">
          <img src="assets/imagen3.jpg" class="img-fluid rounded shadow" alt="Imagen 3">
        </div>
      </div>
    </div>

    <footer class="mt-5">
      <p>© 2025 Mi Sitio Web</p>
    </footer>
  </div>

</body>
</html>
