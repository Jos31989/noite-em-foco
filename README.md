<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Noite em Foco</title>
  <style>
    body {
      margin: 0;
      font-family: sans-serif;
      background: black;
      color: white;
      text-align: center;
      padding: 30px;
    }
    h1 {
      font-size: 3rem;
      color: #ff00ff;
      margin-bottom: 10px;
    }
    .carousel {
      position: relative;
      width: 90%;
      max-width: 600px;
      margin: 40px auto;
      overflow: hidden;
      border-radius: 10px;
      box-shadow: 0 0 20px #ff00ff88;
    }
    .carousel img {
      width: 100%;
      display: none;
    }
    .carousel img.active {
      display: block;
    }
    .buttons {
      margin-top: 10px;
    }
    button {
      padding: 10px 20px;
      margin: 0 10px;
      background: #ff00ff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background: #cc00cc;
    }
  </style>
</head>
<body>
  <h1>Noite em Foco</h1>
  <p>Veja os melhores momentos das baladas 🔥</p>

  <div class="carousel">
    <img src="foto1.jpg" alt="Foto 1" class="active" />
    <img src="foto2.jpg" alt="Foto 2" />
    <img src="foto3.jpg" alt="Foto 3" />
  </div>

  <div class="buttons">
    <button onclick="prev()">◀ Anterior</button>
    <button onclick="next()">Próxima ▶</button>
  </div>

  <script>
    const images = document.querySelectorAll(".carousel img");
    let index = 0;

    function showImage(i) {
      images.forEach(img => img.classList.remove("active"));
      images[i].classList.add("active");
    }

    function next() {
      index = (index + 1) % images.length;
      showImage(index);
    }

    function prev() {
      index = (index - 1 + images.length) % images.length;
      showImage(index);
    }

    // 👇 Troca automática a cada 3 segundos
    setInterval(next, 3000);
  </script>
</body>
</html>
