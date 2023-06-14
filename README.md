# nxwy.shop.xyz

<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-color: #000000;
      color: #ffffff;
      font-family: Arial, sans-serif;
    }
    
    #canvas {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1;
    }
    
    #image-container {
      margin-top: 20px;
      text-align: center;
    }
    
    #image-container img {
      max-width: 100%;
      height: auto;
    }
    
    #button-container {
      text-align: center;
      margin-top: 20px;
    }
    
    #my-button {
      background-color: #ffffff;
      color: #000000;
      padding: 10px 20px;
      border: none;
      cursor: pointer;
      font-size: 16px;
    }
  </style>
</head>
<body>
  <div id="canvas"></div>
  <div id="image-container">
    <img src="path_to_your_image.jpg" alt="Obrázek">
  </div>
  <div id="button-container">
    <button id="my-button">Klikni sem</button>
  </div>

  <script>
    // Přidáme posluchač události na naše tlačítko
    document.getElementById("my-button").addEventListener("click", function() {
      alert("Tlačítko bylo stisknuto!");
    });

    // Vytvoříme tečky na plátně
    var canvas = document.getElementById("canvas");
    var ctx = canvas.getContext("2d");

    // Funkce pro vykreslení tečky
    function drawDot(x, y) {
      ctx.fillStyle = "#ffffff"; // bílá barva
      ctx.beginPath();
      ctx.arc(x, y, 5, 0, 2 * Math.PI);
      ctx.fill();
    }

    // Posluchač události při pohybu myší
    canvas.addEventListener("mousemove", function(event) {
      var rect = canvas.getBoundingClientRect();
      var x = event.clientX - rect.left;
      var y = event.clientY - rect.top;
      drawDot(x, y);
    });
  </script>
</body>
</html>
