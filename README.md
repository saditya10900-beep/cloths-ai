
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Aditya Singh AI Clothes</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background: #0b0b0d;
      color: white;
      font-family: Arial, sans-serif;
    }

    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 22px 7%;
      border-bottom: 1px solid #333;
    }

    .logo {
      color: #e9c778;
      font-weight: bold;
      font-size: 21px;
    }

    nav a {
      color: white;
      text-decoration: none;
      margin-left: 18px;
    }

    .hero {
      text-align: center;
      padding: 80px 20px;
      background: linear-gradient(140deg, #302518, #0b0b0d 70%);
    }

    .hero h1 {
      font-size: clamp(35px, 7vw, 65px);
      margin: 20px 0;
    }

    .hero h1 span {
      color: #e9c778;
    }

    .hero p {
      color: #ccc;
      line-height: 1.8;
      margin-bottom: 25px;
    }

    button {
      background: #e9c778;
      color: #111;
      border: none;
      border-radius: 6px;
      padding: 14px 22px;
      font-weight: bold;
      cursor: pointer;
    }

    section {
      padding: 55px 7%;
    }

    h2 {
      text-align: center;
      margin-bottom: 15px;
    }

    .intro {
      text-align: center;
      color: #aaa;
      margin-bottom: 30px;
    }

    .cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(190px, 1fr));
      gap: 20px;
    }

    .card {
      background: #19191c;
      padding: 28px 18px;
      border: 1px solid #333;
      border-radius: 12px;
      text-align: center;
    }

    .emoji {
      font-size: 45px;
      margin-bottom: 15px;
    }

    .card h3 {
      color: #e9c778;
      margin-bottom: 12px;
    }

    .card p {
      color: #bbb;
      line-height: 1.6;
    }

    .designer {
      max-width: 550px;
      margin: auto;
      padding: 25px;
      background: #19191c;
      border-radius: 12px;
      border: 1px solid #333;
    }

    label {
      display: block;
      margin: 18px 0 8px;
    }

    select {
      width: 100%;
      padding: 13px;
      color: white;
      background: #29292d;
      border: 1px solid #555;
      border-radius: 6px;
    }

    .designer button {
      width: 100%;
      margin-top: 22px;
    }

    #result {
      display: none;
      background: #29251c;
      padding: 18px;
      margin-top: 20px;
      border-radius: 8px;
      line-height: 1.8;
    }

    footer {
      text-align: center;
      padding: 25px;
      color: #aaa;
      border-top: 1px solid #333;
    }

    @media (max-width: 550px) {
      header {
        flex-direction: column;
        gap: 18px;
      }

      nav a {
        margin: 0 6px;
        font-size: 13px;
      }
    }
  </style>
</head>

<body>

  <header>
    <div class="logo">AS | AI CLOTHES</div>
    <nav>
      <a href="#home">Home</a>
      <a href="#styles">Styles</a>
      <a href="#designer">AI Designer</a>
    </nav>
  </header>

  <div class="hero" id="home">
    <p style="color:#e9c778;letter-spacing:4px">
      THE FUTURE OF FASHION
    </p>

    <h1>YOUR STYLE.<br><span>YOUR IDENTITY.</span></h1>

    <p>
      Welcome to Aditya Singh AI Clothes.<br>
      Discover your next outfit with smart fashion ideas.
    </p>

    <button onclick="document.getElementById('designer').scrollIntoView({behavior:'smooth'})">
      CREATE MY OUTFIT
    </button>
  </div>

  <section id="styles">
    <h2>Explore Fashion</h2>
    <p class="intro">Choose a style that matches you.</p>

    <div class="cards">
      <div class="card">
        <div class="emoji">👕</div>
        <h3>Streetwear</h3>
        <p>Oversized tees, cargos and sneakers.</p>
      </div>

      <div class="card">
        <div class="emoji">🤵</div>
        <h3>Luxury</h3>
        <p>Premium shirts, suits and elegant outfits.</p>
      </div>

      <div class="card">
        <div class="emoji">🥻</div>
        <h3>Traditional</h3>
        <p>Festive fashion and traditional looks.</p>
      </div>
    </div>
  </section>

  <section id="designer">
    <h2>AI Outfit Designer ✨</h2>
    <p class="intro">Select your preferences to get an outfit idea.</p>

    <div class="designer">
      <label for="occasion">Occasion</label>
      <select id="occasion">
        <option>College</option>
        <option>Party</option>
        <option>Wedding</option>
        <option>Office</option>
        <option>Casual</option>
      </select>

      <label for="style">Fashion Style</label>
      <select id="style">
        <option>Streetwear</option>
        <option>Luxury</option>
        <option>Traditional</option>
        <option>Minimal</option>
      </select>

      <label for="color">Favourite Colour</label>
      <select id="color">
        <option>Black</option>
        <option>White</option>
        <option>Blue</option>
        <option>Beige</option>
        <option>Olive Green</option>
      </select>

      <button onclick="generateOutfit()">
        GENERATE MY OUTFIT ✨
      </button>

      <div id="result" aria-live="polite"></div>
    </div>
  </section>

  <footer>
    © 2026 Aditya Singh AI Clothes | All Rights Reserved
  </footer>

  <script>
    function generateOutfit() {
      const occasion = document.getElementById("occasion").value;
      const style = document.getElementById("style").value;
      const color = document.getElementById("color").value;

      const suggestions = {
        Streetwear: "Oversized T-shirt, cargo pants and sneakers",
        Luxury: "Premium shirt, tailored trousers and loafers",
        Traditional: "Stylish kurta, matching pants and ethnic shoes",
        Minimal: "Plain shirt, straight-fit trousers and clean sneakers"
      };

      const result = document.getElementById("result");

      result.innerHTML = `
        <h3 style="color:#e9c778">Your Outfit Idea</h3>
        <p><b>Occasion:</b> ${occasion}</p>
        <p><b>Style:</b> ${style}</p>
        <p><b>Colour:</b> ${color}</p>
        <p><b>Outfit:</b> ${suggestions[style]}</p>
        <p>Designed for your personal fashion inspiration!</p>
        <small>This demo uses predefined suggestions, not a live AI model.</small>
      `;

      result.style.display = "block";
    }
  </script>

</body>
</html>
