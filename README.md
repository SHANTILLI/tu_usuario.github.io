<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Acceso Protegido</title>
  <link rel="stylesheet" href="style.css" />
  <script defer src="auth.js"></script>
</head>
<body>
  <div id="contenido" style="display: none;">
    <header>
      <h1>Bienvenido a la Página Secreta</h1>
      <p>Este sitio está protegido con clave.</p>
    </header>

    <main>
      <section>
        <h2>Contenido Privado</h2>
        <p>Solo quienes tienen la clave pueden ver esto.</p>
      </section>
    </main>

    <footer>
      <p>© 2025 - Sitio Seguro</p>
    </footer>
  </div>
</body>
</html>
document.addEventListener("DOMContentLoaded", function () {
  const claveCorrecta = "cargaxpress2025";
  const intento = prompt("Introduce la clave para acceder al sitio:");

  if (intento === claveCorrecta) {
    document.getElementById("contenido").style.display = "block";
  } else {
    document.body.innerHTML = "<h2>Acceso denegado. Clave incorrecta.</h2>";
  }
});
