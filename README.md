<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>La Poción | Jugos online</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f8f5ef;
      color: #3d3128;
    }

    header {
      background: linear-gradient(135deg, #dfead7, #f3ead6);
      padding: 60px 20px;
      text-align: center;
    }

    header h1 {
      margin: 0;
      font-size: 2.7rem;
      color: #2f4f2f;
    }

    header p {
      margin-top: 12px;
      font-size: 1.1rem;
    }

    .container {
      max-width: 800px;
      margin: 0 auto;
      padding: 40px 20px 60px;
    }

    .card {
      background: white;
      border-radius: 18px;
      padding: 24px;
      box-shadow: 0 8px 24px rgba(0,0,0,0.08);
      margin-bottom: 24px;
    }

    h2 {
      margin-top: 0;
      color: #355e3b;
    }

    .prices {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 15px;
      margin-top: 20px;
    }

    .price-box {
      background: #f7fbf4;
      border: 1px solid #d9e6d2;
      border-radius: 14px;
      padding: 16px;
      text-align: center;
    }

    .price-box strong {
      display: block;
      font-size: 1.2rem;
      color: #2f4f2f;
      margin-bottom: 6px;
    }

    label {
      display: block;
      margin-top: 14px;
      margin-bottom: 6px;
      font-weight: bold;
    }

    input, select, textarea {
      width: 100%;
      padding: 13px;
      border: 1px solid #cfc7bb;
      border-radius: 12px;
      font-size: 1rem;
    }

    textarea {
      min-height: 110px;
      resize: vertical;
    }

    .note {
      margin-top: 16px;
      font-size: 0.96rem;
      color: #6b5d52;
      line-height: 1.5;
    }

    .btn {
      margin-top: 20px;
      width: 100%;
      background: #355e3b;
      color: white;
      border: none;
      padding: 15px;
      border-radius: 12px;
      font-size: 1rem;
      cursor: pointer;
    }

    .btn:hover {
      background: #2d4f32;
    }

    .delivery {
      text-align: center;
      background: #fffaf2;
      border: 1px solid #eadfcb;
    }

    footer {
      text-align: center;
      padding: 25px;
      font-size: 0.95rem;
      color: #6b5d52;
    }
  </style>
</head>
<body>

  <header>
    <h1>La Poción</h1>
    <p>Jugos online hechos a tu gusto ✨</p>
  </header>

  <div class="container">

    <div class="card">
      <h2>Tamaños y precios</h2>
      <div class="prices">
        <div class="price-box">
          <strong>12 oz</strong>
          $12
        </div>
        <div class="price-box">
          <strong>16 oz</strong>
          $15
        </div>
        <div class="price-box">
          <strong>24 oz</strong>
          $18
        </div>
      </div>

      <p class="note">
        Todas las botellas incluyen de <strong>1 hasta 3 ingredientes</strong>.<br>
        Si deseas añadir más ingredientes, tienen un costo adicional <strong>desde $2</strong>.
      </p>
    </div>

    <div class="card">
      <h2>Haz tu pedido</h2>

      <label for="name">Nombre</label>
      <input type="text" id="name" placeholder="Tu nombre">

      <label for="size">Tamaño de botella</label>
      <select id="size">
        <option value="">Selecciona una opción</option>
        <option value="12 oz - $12">12 oz - $12</option>
        <option value="16 oz - $15">16 oz - $15</option>
        <option value="24 oz - $18">24 oz - $18</option>
      </select>

      <label for="ingredients">Ingredientes incluidos (1 a 3)</label>
      <textarea id="ingredients" placeholder="Ejemplo: jengibre, limón, china"></textarea>

      <label for="extras">Ingredientes adicionales (+$2 o más)</label>
      <textarea id="extras" placeholder="Escribe aquí si deseas añadir más ingredientes"></textarea>

      <label for="notes">Notas adicionales</label>
      <textarea id="notes" placeholder="Algo que quieras especificar sobre tu orden"></textarea>

      <button class="btn" onclick="sendOrder()">Enviar pedido por WhatsApp</button>
    </div>

    <div class="card delivery">
      <h2>Entregas</h2>
      <p>
        Las entregas son <strong>todos los jueves</strong><br>
        en <strong>Montehiedra</strong><br>
        de <strong>3:00 PM a 6:00 PM</strong>.
      </p>
    </div>

  </div>

  <footer>
    La Poción · Jugos que se sienten bien
  </footer>

  <script>
    const phone = "17874324865";

    function sendOrder() {
      const name = document.getElementById("name").value;
      const size = document.getElementById("size").value;
      const ingredients = document.getElementById("ingredients").value;
      const extras = document.getElementById("extras").value;
      const notes = document.getElementById("notes").value;

      let msg = "Hola, quiero ordenar un jugo en La Poción.%0A%0A";
      msg += "Nombre: " + name + "%0A";
      msg += "Tamaño: " + size + "%0A";
      msg += "Ingredientes incluidos: " + ingredients + "%0A";

      if (extras.trim() !== "") {
        msg += "Ingredientes adicionales: " + extras + "%0A";
      }

      if (notes.trim() !== "") {
        msg += "Notas: " + notes + "%0A";
      }

      msg += "%0AEntrega: Jueves en Montehiedra, de 3:00 PM a 6:00 PM";

      window.open("https://wa.me/" + phone + "?text=" + msg, "_blank");
    }
  </script>

</body>
</html>
