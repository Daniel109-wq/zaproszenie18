<!DOCTYPE html> 
<html lang="pl"> 
<head> 
  <meta charset="UTF-8" /> 
  <meta name="viewport" 
content="width=device-width, 
initial-scale=1.0" /> 
  <title>Zaproszenie</title> 
  <style> 
    body { 
      margin: 0;
      background: #000;
      display: flex;
      justify-content: center; 
      align-items: center;
      height: 100vh; 
      overflow: hidden;
    } 
    .container {
      position: relative;
      width: 320px;
      height: 200px;
      perspective: 1000px;
      cursor: pointer;
    }
    .envelope {
      position: absolute; 
      width: 100%;
      height: 100%;
      background: url('koperta.jpg')
    no-repeat center center / cover;
      border-radius: 10px; 
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
      background: rgba(0, 0, 0, 0.5); 
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
      width: 100%; 
      height: 100%; 
      background: url('zaproszenie.jpg') 
  no-repeat center center / cover;
      border-radius: 10px; 
      transform: translate(-50%, -50%) 
        scale(0); 
      transition: transform 0.5s ease 0.8s; 
      box-shadow: 0 0 20px rgba(255, 255, 255, 0.2); 
    } 
    .envelope.open + .card { transform: translate(-50%, -50%) scale(1); } </style> </head> <body> <div class="container" onclick="openEnvelope()"> <div class="envelope" id="envelope"> <div class="flap"></div> </div> <div class="card" id="card"></div> </div> <!-- Muzyka --> <audio id="bg-music" src="muzyka.mp3" preload="auto"></audio> <script> function openEnvelope() { const envelope = document.getElementById("envelope"); envelope.classList.add("open"); const music = document.getElementById("bg-music"); music.play(); } </script> </body> </html> 
