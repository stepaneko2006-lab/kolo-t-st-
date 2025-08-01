# kolo-t-st-
<!DOCTYPE html>
<html lang="cs">
<head>
  <meta charset="UTF-8">
  <title>Kolo štěstí</title>
  <style>
    body {
      margin: 0;
      background-color: #FFE5B4; /* světle oranžová */
      font-family: sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .wrapper {
      position: relative;
      width: 500px;
      height: 500px;
    }

    .background {
      position: absolute;
      width: 100%;
      height: 100%;
      display: flex;
    }

    .sunset {
      background: linear-gradient(to right, #6a0572, #8e44ad); /* fialový západ slunce */
      width: 50%;
      height: 100%;
    }

    .sunrise {
      background: linear-gradient(to right, #f39c12, #f1c40f); /* oranžový východ slunce */
      width: 50%;
      height: 100%;
    }

    #wheel {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) rotate(0deg);
      width: 300px;
      height: 300px;
      border-radius: 50%;
      border: 10px solid #333;
      background: conic-gradient(#ff7675 0% 25%, #74b9ff 25% 50%, #55efc4 50% 75%, #ffeaa7 75% 100%);
    }

    button {
      position: absolute;
      bottom: -60px;
      left: 50%;
      transform: translateX(-50%);
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
  <div class="wrapper">
    <div class="background">
      <div class="sunset"></div>
      <div class="sunrise"></div>
    </div>
    <div id="wheel"></div>
    <button onclick="spinWheel()">Toč!</button>
  </div>

  <script>
    function spinWheel() {
      const wheel = document.getElementById('wheel');
      const rotation = Math.floor(Math.random() * 360) + 1080; // alespoň 3 otáčky
      wheel.style.transition = 'transform 4s ease-out';
      wheel.style.transform = `translate(-50%, -50%) rotate(${rotation}deg)`;
    }
  </script>
</body>
</html>
