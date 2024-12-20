<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>P5.js Interaction with HTML</title>
  <style>
    body {
      text-align: center;
      font-family: Arial, sans-serif;
      background-color: #f0f0f0;
    }
    #container {
      margin: 20px auto;
      width: 800px;
      height: 600px;
      border: 2px solid #000;
      position: relative;
    }
    button {
      margin: 10px;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <h1>Interactive P5.js Canvas</h1>
  <button id="startButton">Start Animation</button>
  <button id="stopButton">Stop Animation</button>

  <button id="colorButton">Change Particle Color</button>
 
  <div id="container"></div>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.5.0/p5.js"></script>
  <script>
let isAnimating = false; // 控制动画的开关
let particles = [];

function setup() {
  // 将画布嵌入到HTML中的指定容器
  let canvas = createCanvas(800, 600);
  canvas.parent('container');
  background(0);

  // 获取HTML按钮元素并绑定事件
  let startButton = select('#startButton');
  let stopButton = select('#stopButton');
  
  let colorButton = select('#colorButton'); 

  startButton.mousePressed(startAnimation);
  stopButton.mousePressed(stopAnimation);
   
  colorButton.mousePressed(() => {
  for (let p of particles) {
    p.size = random(5, 60); // 随机改变粒子大小
  }
});

}

function draw() {
  if (isAnimating) {
    background(0, 20); // 半透明背景效果，产生尾迹
    for (let p of particles) {
      p.move();
      p.show();
    }
  }
}

function startAnimation() {
  isAnimating = true;
  for (let i = 0; i < 100; i++) {
    particles.push(new Particle(random(width), random(height)));
  }
}

function stopAnimation() {
  isAnimating = false;
  particles = []; // 清空粒子数组
}

class Particle {
  constructor(x, y) {
    this.x = x;
    this.y = y;
    this.vx = random(-2, 2);
    this.vy = random(-2, 2);
    this.size = random(5, 15);
  }

  move() {
    this.x += this.vx;
    this.y += this.vy;
    if (this.x > width || this.x < 0) this.vx *= -1;
    if (this.y > height || this.y < 0) this.vy *= -1;
  }

  show() {
    noStroke();
    fill(255, random(100, 255));
    ellipse(this.x, this.y, this.size);
  }
}


  </script>
</body>
</html>
