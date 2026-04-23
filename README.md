<!DOCTYPE html>

<html lang="en">

<head>

  <meta charset="UTF-8">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Algebra Game Hub</title>

  <style>

    body { font-family: Arial, sans-serif; margin: 0; background: #0f172a; color: white; }

    header { background: #1e293b; padding: 15px; text-align: center; }

    h1 { margin: 0; }

    .container { padding: 20px; }

    .game { background: #1e293b; padding: 15px; margin-bottom: 15px; border-radius: 10px; }

    button { padding: 10px 15px; border: none; border-radius: 8px; cursor: pointer; background: #38bdf8; }

    iframe { width: 100%; height: 400px; border: none; border-radius: 10px; }

  </style>

</head>

<body>

<header>

  <h1>Algebra Game Hub</h1>

  <p>Connected to algebra.rest</p>

</header>

<div class="container">

  <div class="game">

    <h2>Live Algebra API</h2>

    <button onclick="solveProblem()">Solve Example Problem</button>

    <p id="result"></p>

  </div>

  <div class="game">

    <h2>Embedded Site</h2>

    <iframe src="https://algebra.rest"></iframe>

  </div>

  <div class="game">

    <h2>Auto Game Loader (Simulated)</h2>

    <button onclick="loadGame()">Load New Game</button>

    <div id="games"></div>

  </div>

</div>

<script>

async function solveProblem() {

  const res = await fetch('https://algebra.rest/simplify?expression=2x+3x');

  const data = await res.json();

  document.getElementById('result').innerText = "Answer: " + data.result;

}

function loadGame() {

  const gameContainer = document.getElementById('games');

  const newGame = document.createElement('div');

  newGame.innerHTML = "<p>New Game Added! Solve: 5x + 2x = ?</p>";

  gameContainer.appendChild(newGame);

}

</script>

</body>

</html>
