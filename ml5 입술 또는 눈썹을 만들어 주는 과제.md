## p5.js에서 ml5 사용

p5에서 ml5을 사용하려면 html의 head에서 ml5 라이브러리를 script로 등록해주어야 한다.

```sql
<script src="https://unpkg.com/ml5@latest/dist/ml5.min.js"></script>
```

---

### ****[페이스 마스크 만들기 : Face-Api](https://wikidocs.net/103515)****

```jsx
let img, parts;
let options = {withLandmarks: true, withDescriptors: false};

function preload() {
  img = loadImage('face.png');
}

function setup() {
  createCanvas(img.width*2, img.height);
  faceapi = ml5.faceApi(options, modelReady);
  background(255);
  image(img, img.width, 0);    
}

function modelReady() {
  faceapi.detectSingle(img, gotResults);
}

function gotResults(err, results) {
  if (err) {
    console.error(err);
    return;
  }
  console.log(results);
  parts = results.parts;
  noFill();
  stroke(0, 0, 255);
  strokeWeight(3);
  drawFace();
}

function drawFace() {
  stroke(255, 0, 255);

  //입술그리기
  beginShape();
  for(let i=0; i<parts.mouth.length; i++){
    vertex(parts.mouth[i]._x, parts.mouth[i]._y);
  }
  vertex(parts.mouth[0]._x, parts.mouth[0]._y);
  endShape();

  //코 그리기    
  beginShape();
  for(let i=0; i<parts.nose.length; i++){
    vertex(parts.nose[i]._x, parts.nose[i]._y);
  }
  endShape();

  //눈 그리기
  fill(100);
  beginShape();
  for(let i=0; i<parts.leftEye.length; i++){
    vertex(parts.leftEye[i]._x, parts.leftEye[i]._y);
  }
  vertex(parts.leftEye[0]._x, parts.leftEye[0]._y);
  endShape();

  beginShape();
  for(let i=0; i<parts.rightEye.length; i++){
    vertex(parts.rightEye[i]._x, parts.rightEye[i]._y);
  }
  vertex(parts.rightEye[0]._x, parts.rightEye[0]._y);
  endShape();

  //눈썹 그리기    
  noFill();
  beginShape();
  for(let i=0; i<parts.leftEyeBrow.length; i++){
    vertex(parts.leftEyeBrow[i]._x, parts.leftEyeBrow[i]._y);
  }
  endShape();

  beginShape();
  for(let i=0; i<parts.rightEyeBrow.length; i++){
    vertex(parts.rightEyeBrow[i]._x, parts.rightEyeBrow[i]._y);
  }
  endShape();
}
```

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/a115760d-d6cb-48da-8281-9c7dbcf35fd5/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220509%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220509T130951Z&X-Amz-Expires=86400&X-Amz-Signature=8fa80b837fd744fe7062c31b1445c5c96ebc6da7e3f3950fb52b2eeb4e2cac0d&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

---

### 코드 수정

```jsx
let img, parts;
let options = {withLandmarks: true, withDescriptors: false};

function preload() {
  img = loadImage('face.png');
}

function setup() {
  createCanvas(img.width*2, img.height);
  faceapi = ml5.faceApi(options, modelReady);
  background(255);
  image(img, img.width, 0);    
  image(img, 0, 0);    
}

function modelReady() {
  faceapi.detectSingle(img, gotResults);
}

function gotResults(err, results) {
  if (err) {
    console.error(err);
    return;
  }
  console.log(results);
  parts = results.parts;
  noFill();
  stroke(0, 0, 255);
  strokeWeight(3);
  drawFace();
}

function drawFace() {
  stroke(255, 0, 255);

  //입술그리기
  push();
  beginShape();
  for(let i=0; i<parts.mouth.length; i++){
    fill(255,0,0);
    vertex(parts.mouth[i]._x, parts.mouth[i]._y);
  }
  vertex(parts.mouth[0]._x, parts.mouth[0]._y);
  endShape();
  pop();
  //코 그리기    
  beginShape();
  for(let i=0; i<parts.nose.length; i++){
    vertex(parts.nose[i]._x, parts.nose[i]._y);
  }
  endShape();

  //눈 그리기
  fill(100);
  beginShape();
  for(let i=0; i<parts.leftEye.length; i++){
    vertex(parts.leftEye[i]._x, parts.leftEye[i]._y);
  }
  vertex(parts.leftEye[0]._x, parts.leftEye[0]._y);
  endShape();

  beginShape();
  for(let i=0; i<parts.rightEye.length; i++){
    vertex(parts.rightEye[i]._x, parts.rightEye[i]._y);
  }
  vertex(parts.rightEye[0]._x, parts.rightEye[0]._y);
  endShape();

  //눈썹 그리기    
  push();
  noFill();
  strokeWeight(10);
  beginShape();
  for(let i=0; i<parts.leftEyeBrow.length; i++){
    vertex(parts.leftEyeBrow[i]._x, parts.leftEyeBrow[i]._y);
  }
  endShape();
  pop();
  beginShape();
  for(let i=0; i<parts.rightEyeBrow.length; i++){
    strokeWeight(10);
    vertex(parts.rightEyeBrow[i]._x, parts.rightEyeBrow[i]._y);
  }
  endShape();
}
```

예제 코드에서 입부분과 눈썹부분을 수정했다.

입부분을 빨간색으로 색칠( Fill(255,0,0); )

눈썹부분의 strokeWeight를 20을 주었다.

![<결과>](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/bb9ffbc2-9809-42f7-9f6c-2b90865b4e21/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220509%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220509T130657Z&X-Amz-Expires=86400&X-Amz-Signature=0639ee9b11eff920e562e2a50477199d8b50b55e67e38c267c9f21fd608b6a65&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

<결과>
