# Basketball-game
<!DOCTYPE html>
<html>
<head>
  <title>Basketball Game</title>
  <style>
    body {
      font-family: Arial;
      text-align: center;
      margin: 0;
      padding: 0;
      background: #87ceeb;
      overflow-y: auto;
    }

    h1 {
      margin-top: 20px;
    }

    #court {
      position: relative;
      width: 100%;
      height: 500px;
      border: 3px solid #333;
      background: #4caf50;
      margin-top: 20px;
    }

    #ball {
      position: absolute;
      font-size: 50px;
      cursor: pointer;
      left: 50px;
      bottom: 50px;
      transition: all 0.6s ease;
    }

    #hoop {
      position: absolute;
      font-size: 60px;
      right: 100px;
      top: 100px;
    }

    #score {
      font-size: 24px;
      margin-top: 10px;
    }
  </style>
</head>

<body>

<h1>🏀 Basketball Shooting Game</h1>
<p>Click the basketball to shoot!</p>

<div id="score">Score: 0</div>

<div id="court">
  <div id="hoop">🧺</div>
  <div id="ball" onclick="shoot()">🏀</div>
</div>

<script>
  let score = 0;
  let shooting = false;

  function shoot() {
    if (shooting) return;
    shooting = true;

    let ball = document.getElementById("ball");

    // Move ball toward hoop
    ball.style.left = "80%";
    ball.style.bottom = "70%";

    setTimeout(() => {
      score++;
      document.getElementById("score").innerText = "Score: " + score;

      // reset ball
      ball.style.left = "50px";
      ball.style.bottom = "50px";

      shooting = false;
    }, 700);
  }
</script>

</body>
</html>
