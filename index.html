let playerRole = ''; // 'bat' or 'bowl'
let playerScore = 0;
let botScore = 0;
let wickets = 0;
let balls = 0;
let maxBalls = 12;
let isFirstInnings = true;
let gameOver = false;
let previousPlayerMoves = [];

function toss(choice) {
  const playerNum = Math.ceil(Math.random() * 6);
  const botNum = Math.ceil(Math.random() * 6);
  const sum = playerNum + botNum;
  const won = (sum % 2 === 0 && choice === 'even') || (sum % 2 !== 0 && choice === 'odd');

  document.getElementById('toss-section').style.display = 'none';

  if (won) {
    document.getElementById('choose-role').style.display = 'block';
  } else {
    playerRole = Math.random() > 0.5 ? 'bowl' : 'bat';
    document.getElementById('gameplay').style.display = 'block';
    updateStatus(`Bot chose to ${playerRole === 'bat' ? 'bowl' : 'bat'}.`);
  }
}

function setPlayerRole(role) {
  playerRole = role;
  document.getElementById('choose-role').style.display = 'none';
  document.getElementById('gameplay').style.display = 'block';
  updateStatus(`You chose to ${role}.`);
}

function play(playerInput) {
  if (gameOver) return;

  const botInput = hardBotChoice();
  previousPlayerMoves.push(playerInput);
  if (previousPlayerMoves.length > 5) previousPlayerMoves.shift();

  const isPlayerBatting = (isFirstInnings && playerRole === 'bat') || (!isFirstInnings && playerRole === 'bowl');

  if (playerInput === botInput) {
    updateLog(`You: ${playerInput} | Bot: ${botInput} → OUT!`);
    wickets++;
    if (wickets >= 1 || balls >= maxBalls) changeInnings();
  } else {
    const runs = isPlayerBatting ? playerInput : botInput;
    if (isPlayerBatting) playerScore += runs;
    else botScore += runs;

    updateLog(`You: ${playerInput} | Bot: ${botInput} → ${runs} run(s)`);
  }

  balls++;
  updateScore();

  if (balls >= maxBalls && !gameOver) changeInnings();
}

function updateLog(msg) {
  document.getElementById('log').innerText = msg;
}

function updateScore() {
  document.getElementById('score').innerText = `Score: ${playerScore}/${wickets}`;
}

function updateStatus(msg) {
  document.getElementById('status').innerText = msg;
}

function changeInnings() {
  if (isFirstInnings) {
    isFirstInnings = false;
    balls = 0;
    wickets = 0;
    updateLog('');
    updateStatus(`2nd Innings: ${playerRole === 'bat' ? 'Bot batting' : 'You batting'}`);
  } else {
    gameOver = true;
    document.getElementById('gameplay').style.display = 'none';
    document.getElementById('result').style.display = 'block';

    let resultText = '';
    if (playerScore > botScore) resultText = '🎉 You won!';
    else if (playerScore < botScore) resultText = '💀 Bot wins!';
    else resultText = '🤝 Match Draw!';

    document.getElementById('result').innerText = `Final Score\nYou: ${playerScore}\nBot: ${botScore}\n${resultText}`;
  }
}

// Simple prediction bot using previous player patterns
function hardBotChoice() {
  if (previousPlayerMoves.length < 3) return Math.ceil(Math.random() * 6);

  const freq = [0, 0, 0, 0, 0, 0];
  for (let move of previousPlayerMoves) freq[move - 1]++;

  let maxFreq = Math.max(...freq);
  let likely = freq.findIndex(f => f === maxFreq) + 1;

  // Slight randomness to avoid being too predictable
  return Math.random() < 0.7 ? likely : Math.ceil(Math.random() * 6);
}
