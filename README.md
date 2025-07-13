# zaproszenie18
<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Zaproszenie</title>
  <style>
    body {
      margin: 0;
      background: #fdf6e3;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: 'Arial', sans-serif;
      overflow: hidden;
    }

    .container {
      position: relative;
      width: 300px;
      height: 200px;
      perspective: 1000px;
      cursor: pointer;
    }

    .envelope {
      position: absolute;
      width: 100%;
      height: 100%;
      background: #d33c44;
      border-radius: 8px;
      transform-style: preserve-3d;
      transition: transform 1s ease;
    }

    .envelope.open {
      transform: rotateX(180deg);
    }

    .flap {
      position: absolute;
      top: 0;
      width: 100%;
      height: 50%;
      background: #b02c35;
      border-radius: 8px 8px 0 0;
      transform-origin: top;
      transform: rotateX(0deg);
      transition: transform 1s ease;
      z-index: 2;
    }

    .envelope.open .flap {
      transform: rotateX(-180deg);
    }

    .card {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 90%;
      height: 80%;
      background: #fff;
      color: #000;
      border-radius: 10px;
      transform: translate(-50%, -50%) scale(0);
      transition: transform 0.5s ease 0.8s;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 1.2em;
      text-align: center;
      padding: 10px;
      box-shadow: 0 5px 20px rgba(0,0,0,0.2);
    }

    .envelope.open + .card {
      transform: translate(-50%, -50%) scale(1);
    }
  </style>
</head>
<body>
  <div class="container" onclick="openEnvelope()">
    <div class="envelope" id="envelope">
      <div class="flap"></div>
    </div>
    <div class="card" id="card">
      Zaproszenie na 18-stkę!
    </div>
  </div>

  <script>
    function openEnvelope() {
      document.getElementById("envelope").classList.add("open");
    }
  </script>
</body>
</html>
