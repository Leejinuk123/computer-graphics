> ## 지형을 camera와 Light 그리고 Metarial을 적용하여 변형하시오

### p5.js Code
```p5.js
var cols, rows;
var scl = 20;
var w = 1400;
var h = 1000;

var flying = 0;

var terrain = [];

function setup() {
createCanvas(600, 600, WEBGL);
cols = w / scl;
rows = h / scl;

for (var x = 0; x < cols; x++) {
terrain[x] = [];
for (var y = 0; y < rows; y++) {
terrain[x][y] = 0; //specify a default value for now
}
}
noStroke();
}

function draw() {
  
flying -= 0.1;
var yoff = flying;
for (var y = 0; y < rows; y++) {
var xoff = 0;
for (var x = 0; x < cols; x++) {
terrain[x][y] = map(noise(xoff, yoff), 0, 1, -100, 100);
xoff += 0.2;
}
yoff += 0.2;
}
background(0);
camera(100, 100, 1000 + sin(frameCount * 0.1) * 200, 0, 0, 0, 0, 1, 0);
translate(0, 50);
rotateX(PI / 3);

push();
  translate(-width / 4, -height / 4, 0);
  rotateZ(frameCount * 0.01);
  rotateX(frameCount * 0.01);
  rotateY(frameCount * 0.01);
  fill(250, 0, 0);
  torus(80, 20, 64, 64);
pop();
  
push();
  translate(-width / 4, -height / 4, 0);
  rotateZ(frameCount * 0.01);
  rotateX(frameCount * 0.01);
  rotateY(frameCount * 0.01);
  fill(250, 0, 0);
  torus(80, 20, 64, 64);
pop();

push();
  translate(width / 4, -height / 4, 0);
  rotateZ(frameCount * 0.01);
  rotateX(frameCount * 0.01);
  rotateY(frameCount * 0.01);
  normalMaterial();
  torus(80, 20, 64, 64);
pop();

push();
  translate(-width / 4, height / 4, 0);
  rotateZ(frameCount * 0.01);
  rotateX(frameCount * 0.01);
  rotateY(frameCount * 0.01);
  ambientMaterial(250);
  torus(80, 20, 64, 64);
pop();

push();
  translate(width / 4, height / 4, 0);
  rotateZ(frameCount * 0.01);
  rotateX(frameCount * 0.01);
  rotateY(frameCount * 0.01);
  specularMaterial(250);
  torus(80, 20, 64, 64);
pop();

translate(-w / 2, -h / 2);
for (var y = 0; y < rows - 1; y++) {
beginShape(TRIANGLE_STRIP);
for (var x = 0; x < cols; x++) {
fill(terrain[x][y],128-terrain[x][y], 255+terrain[x][y]);
//fill(map(terrain[x][y],-100,100,0,255));
vertex(x * scl, y * scl, terrain[x][y]);
vertex(x * scl, (y + 1) * scl, terrain[x][y + 1]);
  }
endShape();
}
  
push();
  translate(mouseX * 2.3,mouseY);
  ambientLight(50);
  spotLight(0, 0, 0, mouseX, mouseY, 500, 0, 0, -1, Math.PI / 16);
  noStroke();
  sphere(40);
pop();

}
```
### 마우스를 따랑 움직이는 spotlight와 4개의 torus에 Metarial을 적용시켰습니다.
---
## 실행 화면
![2022-04-03-20-49-40_Trim_Trim](https://user-images.githubusercontent.com/50895677/161426947-a31586ef-fa0a-487d-8ec0-96420360e33f.gif)

