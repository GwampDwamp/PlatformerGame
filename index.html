const canvas = document.getElementById("gameCanvas");
const ctx = canvas.getContext("2d");

// Game variables
const keys = {};
const gravity = 0.5;
const groundLevel = 350;
let mouseX = 0;
let mouseY = 0;

let player = {
    x: 100,
    y: 0,
    width: 40,
    height: 50,
    color: "cyan",
    dx: 0,
    dy: 0,
    speed: 4,
    jumping: false,
    health: 100
};

let bullets = [];
let enemies = [];

function spawnEnemy() {
    enemies.push({
        x: 800,
        y: groundLevel - 40,
        width: 40,
        height: 40,
        color: "red",
        dx: -1.5,
        health: 3
    });
}

setInterval(spawnEnemy, 3000); // Spawn every 3s

document.addEventListener("keydown", e => keys[e.key] = true);
document.addEventListener("keyup", e => keys[e.key] = false);

// Track mouse
canvas.addEventListener("mousemove", e => {
    const rect = canvas.getBoundingClientRect();
    mouseX = e.clientX - rect.left;
    mouseY = e.clientY - rect.top;
});

canvas.addEventListener("mousedown", e => {
    if (e.button === 0) shootTowardMouse();
});

function shootTowardMouse() {
    const px = player.x + player.width / 2;
    const py = player.y + player.height / 2;

    const angle = Math.atan2(mouseY - py, mouseX - px);
    const speed = 7;

    bullets.push({
        x: px,
        y: py,
        width: 10,
        height: 5,
        dx: Math.cos(angle) * speed,
        dy: Math.sin(angle) * speed,
        color: "yellow"
    });
}

function updatePlayer() {
    if (keys["ArrowRight"] || keys["d"]) player.dx = player.speed;
    else if (keys["ArrowLeft"] || keys["a"]) player.dx = -player.speed;
    else player.dx = 0;

    if ((keys["ArrowUp"] || keys["w"]) && !player.jumping) {
        player.dy = -10;
        player.jumping = true;
    }

    player.dy += gravity;
    player.x += player.dx;
    player.y += player.dy;

    if (player.y + player.height >= groundLevel) {
        player.y = groundLevel - player.height;
        player.dy = 0;
        player.jumping = false;
    }

    player.x = Math.max(0, Math.min(canvas.width - player.width, player.x));
}

function updateBullets() {
    bullets = bullets.filter(b => {
        b.x += b.dx;
        b.y += b.dy;
        return b.x >= 0 && b.x <= canvas.width && b.y >= 0 && b.y <= canvas.height;
    });
}

function updateEnemies() {
    enemies.forEach((e, ei) => {
        e.x += e.dx;

        if (collides(player, e)) {
            player.health -= 1;
        }

        bullets.forEach((b, bi) => {
            if (collides(b, e)) {
                e.health--;
                bullets.splice(bi, 1);
                if (e.health <= 0) enemies.splice(ei, 1);
            }
        });
    });
}

function collides(a, b) {
    return a.x < b.x + b.width &&
           a.x + a.width > b.x &&
           a.y < b.y + b.height &&
           a.y + a.height > b.y;
}

function draw() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);

    ctx.fillStyle = "#444";
    ctx.fillRect(0, groundLevel, canvas.width, canvas.height - groundLevel);

    ctx.fillStyle = player.color;
    ctx.fillRect(player.x, player.y, player.width, player.height);

    bullets.forEach(b => {
        ctx.fillStyle = b.color;
        ctx.fillRect(b.x, b.y, b.width, b.height);
    });

    enemies.forEach(e => {
        ctx.fillStyle = e.color;
        ctx.fillRect(e.x, e.y, e.width, e.height);
    });

    ctx.fillStyle = "white";
    ctx.font = "20px Arial";
    ctx.fillText(`Health: ${player.health}`, 10, 30);
}

function gameLoop() {
    updatePlayer();
    updateBullets();
    updateEnemies();
    draw();

    if (player.health > 0) {
        requestAnimationFrame(gameLoop);
    } else {
        ctx.fillStyle = "white";
        ctx.font = "50px Arial";
        ctx.fillText("Game Over", canvas.width / 2 - 150, canvas.height / 2);
    }
}

gameLoop();
