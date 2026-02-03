const express = require("express");
const app = express();

app.use(express.json());

let scores = [];

app.get("/", (req, res) => {
  res.send(`
    <!DOCTYPE html>
    <html>
    <head>
      <title>Pong Scores API</title>
      <style>
        body {
          font-family: 'Courier New', monospace;
          background: #0a0a0a;
          color: #00ff66;
          padding: 40px;
          text-align: center;
        }
        h1 { text-shadow: 0 0 10px #00ff66; }
        .status { 
          background: #1a1a1a;
          border: 2px solid #00ff66;
          padding: 20px;
          border-radius: 10px;
          margin: 20px auto;
          max-width: 600px;
        }
        button {
          background: #00ff66;
          color: #000;
          border: none;
          padding: 10px 20px;
          margin: 10px;
          border-radius: 5px;
          cursor: pointer;
          font-weight: bold;
        }
        pre {
          background: #2a2a2a;
          padding: 15px;
          border-radius: 5px;
          text-align: left;
        }
      </style>
    </head>
    <body>
      <h1>🎮 Pong Scores API</h1>
      <div class="status">
        <h2>✅ Servidor Activo</h2>
        <p>Total: <span id="count">0</span></p>
        <button onclick="testAPI()">Probar API</button>
        <button onclick="viewScores()">Ver Scores</button>
      </div>
      <pre id="result"></pre>
      <script>
        async function testAPI() {
          const res = await fetch('/api/record');
          const data = await res.json();
          document.getElementById('result').textContent = JSON.stringify(data, null, 2);
        }
        async function viewScores() {
          const res = await fetch('/api/scores');
          const data = await res.json();
          document.getElementById('result').textContent = JSON.stringify(data, null, 2);
          document.getElementById('count').textContent = data.length;
        }
        viewScores();
      </script>
    </body>
    </html>
  `);
});

app.get("/api/record", (req, res) => {
  if (scores.length === 0) {
    return res.json({ record: 0, holder: "Nadie", message: "No hay récords" });
  }
  const best = scores.reduce((max, c) => (c.score > max.score ? c : max));
  res.json({ record: best.score, holder: best.playerName, date: best.date });
});

app.get("/api/scores", (req, res) => {
  res.json(scores.sort((a, b) => b.score - a.score).slice(0, 10));
});

app.post("/api/scores", (req, res) => {
  const { playerName, score } = req.body;
  if (!playerName || typeof score !== "number") {
    return res.status(400).json({ error: "Datos inválidos" });
  }
  const newScore = {
    playerName: playerName.substring(0, 50),
    score: Math.floor(score),
    date: new Date().toISOString(),
  };
  scores.push(newScore);
  console.log(`✅ Score: ${playerName} - ${score} pts`);
  res.json({ success: true, data: newScore });
});

const PORT = 3000;
app.listen(PORT, () => console.log("🎮 API corriendo en puerto " + PORT));
