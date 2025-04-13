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
  <div id="auth-modal" class="modal">
    <div class="modal-content">
      <h2>🔐 Acceso Restringido</h2>
      <p>Introduce la clave para acceder al sitio:</p>
      <input type="password" id="clave-input" placeholder="Clave secreta" />
      <button onclick="verificarClave()">Ingresar</button>
      <p id="error-msg" class="error-msg"></p>
    </div>
  </div>

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
body {
  font-family: 'Segoe UI', sans-serif;
  margin: 0;
  padding: 0;
  background: #eef2f3;
  color: #333;
}

header {
  background-color: #0077cc;
  color: white;
  padding: 2rem;
}

main {
  padding: 2rem;
}

footer {
  background-color: #111;
  color: white;
  padding: 1rem;
  margin-top: 2rem;
  text-align: center;
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.8);
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-content {
  background-color: #fff;
  padding: 2rem;
  border-radius: 10px;
  text-align: center;
  width: 300px;
}

.modal-content input {
  padding: 0.5rem;
  margin-top: 1rem;
  width: 100%;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.modal-content button {
  margin-top: 1rem;
  padding: 0.5rem 1rem;
  background-color: #0077cc;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.modal-content button:hover {
  background-color: #005fa3;
}

.error-msg {
  color: red;
  margin-top: 0.5rem;
}
function verificarClave() {
  const claveCorrecta = "cargaxpress2025";
  const inputClave = document.getElementById("clave-input").value;
  const errorMsg = document.getElementById("error-msg");

  if (inputClave === claveCorrecta) {
    document.getElementById("auth-modal").style.display = "none";
    document.getElementById("contenido").style.display = "block";
  } else {
    errorMsg.textContent = "Clave incorrecta. Intenta de nuevo.";
  }
}

