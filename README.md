# kolostesti
<!DOCTYPE html>
<html lang="cs">
<head>
  <meta charset="UTF-8">
  <title>Kolo štěstí</title>
  <style>
    body {
      margin: 0;
      background-color: #FFE5B4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: sans-serif;
    }

    .wheel-container {
      position: relative;
      width: 300px;
      height: 300px;
    }

    .wheel {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      border: 10px solid #333;
      background: conic-gradient(
        #6a0572 0deg 180deg,
        #f39c12 180deg 360deg
      );
      transition: transform 4s ease-out;
    }

    .pointer {
      position: absolute;
      top: -20px;
      left: 50%;
      transform: translateX(-50%);
      width: 0;
      height: 0;
      border-left: 15px solid transparent;
      border-right: 15px solid transparent;
      border-bottom: 20px solid #333;
      z-index: 10;
    }

    button {
      margin-top: 30px;
      padding: 10px 20px;
      font-size: 16px;
      background-color: #333;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div style="text-align: center;">
    <div class="wheel-container">
      <div class="pointer"></div>
      <div id="wheel" class="wheel"></div>
    </div>
    <button onclick="spinWheel()">Toč!</button>
  </div>

  <script>
    function spinWheel() {
      const wheel = document.getElementById('wheel');
      const rotation = Math.floor(Math.random() * 360) + 1080;
      wheel.style.transform = `rotate(${rotation}deg)`;
    }
  </script>
</body>
</html>
