<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>IRL - Color Trend</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background: #f4f4f4;
      color: #333;
      text-align: center;
    }
    header {
      background: #222;
      color: #fff;
      padding: 1rem;
    }
    main {
      padding: 2rem;
    }
    .color-box {
      padding: 2rem;
      margin: 2rem auto;
      width: 200px;
      border-radius: 10px;
      font-size: 1.5rem;
      font-weight: bold;
      color: #fff;
    }
    .update-section {
      margin-top: 2rem;
    }
    input[type="text"] {
      padding: 0.5rem;
      font-size: 1rem;
    }
    button {
      padding: 0.5rem 1rem;
      font-size: 1rem;
      background: #28a745;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      margin-top: 0.5rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>IRL - Today’s Color Trend</h1>
  </header>
  <main>
    <div id="colorDisplay" class="color-box" style="background: gray;">
      Loading Color...
    </div><div class="update-section">
  <h3>Update Today's Color</h3>
  <input type="text" id="colorInput" placeholder="Enter Red / Green / Violet" />
  <br />
  <button onclick="updateColor()">Update Color</button>
</div>

  </main>  <script>
    // Default color
    let todayColor = localStorage.getItem("irlColor") || "Gray";

    function renderColor() {
      const box = document.getElementById("colorDisplay");
      box.textContent = todayColor;
      box.style.background = todayColor.toLowerCase();
    }

    function updateColor() {
      const input = document.getElementById("colorInput").value.trim();
      if (input === "" || !["red", "green", "violet"].includes(input.toLowerCase())) {
        alert("Please enter Red, Green, or Violet");
        return;
      }
      todayColor = input;
      localStorage.setItem("irlColor", input);
      renderColor();
    }

    // Initial render
    renderColor();
  </script></body>
</html>
