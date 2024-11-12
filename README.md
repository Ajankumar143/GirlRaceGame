<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Girl Race</title>
    <style>
        /* Add your CSS here */
    </style>
</head>
<body>
    <canvas id="gameCanvas" width="320" height="480"></canvas>
    <script>
        const canvas = document.getElementById('gameCanvas');
const ctx = canvas.getContext('2d');

// Game variables
let girlX = 40;
let girlY = 0;
let pipeY = 0;
let score = 0;

// Jumping variables
let isJumping = false;
let gravity = 0.98;
let minJumpTime = 100;
let maxJumpTime = 200;
let jumpTime = minJumpTime;

// Pipe variables
let pipeGap = 150;
let pipeSpeed = 5;
let pipeWidth = 50;
let pipeHeight = 200;

// Functions
function update() {
    if (!isJumping) {
        girlY += gravity;
    }

    if (girlY >= canvas.height - pipeHeight) {
        gameOver();
    }

    if (pipeY <= 0) {
        pipeY = canvas.height - pipeHeight;
        pipeX = Math.random() * (canvas.width - pipeWidth);
    }

    pipeY -= pipeSpeed;

    draw();
    requestAnimationFrame(update);
}

function draw() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);

    // Draw girl
    ctx.beginPath();
    ctx.fillStyle = '#000';
    ctx.rect(girlX, girlY, 20, 40);
    ctx.fill();

    // Draw pipes
    ctx.beginPath();
    ctx.fillStyle = '#000';
    ctx.rect(pipeX, pipeY, pipeWidth, pipeHeight);
    ctx.fill();

    // Draw ground
    ctx.beginPath();
    ctx.fillStyle = '#000';
    ctx.rect(0, canvas.height - 20, canvas.width, 20);
    ctx.fill();

    // Update score
    document.getElementById('score').innerHTML = score;
}

function jump() {
    if (!isJumping) {
        isJumping = true;
        girlY -= 50;
    </script>
</body>body {
    background-color: #f0f0f0;
}

canvas {
    background-color: #f0f0f0;
}

#score {
    position: absolute;
    top: 10px;
    left: 10px;
    font-size: 24px;
    font-weight: bold;
}
</html>




















































































