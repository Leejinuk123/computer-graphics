> ## 1. 프로세싱 사각 도형 만들기( 마우스와 인터렉티브하기 )
## 핵심 Keywords :
    rectMode(CENTER) : 사각형의 생성 위치를 정해준다. 기본은 왼쪽 상단이 중심이 된다.
    translate() : 위치를 이동시켜준다.
    rotate() : 회전 각도를 정해준다.
    scale() : 크기를 정해준다.
    rect() : 사각형을 그려준다.
    
* * *

## 예시 : 
```processing
void setup(){ //initial
  size(500,500);
  rectMode(CENTER);
}
float f=0;
void draw(){ //loop part
  translate(mouseX, mouseY); //translate = move
  rotate(f); //rotation
  scale( sin(f)+1); //sin(f) = -1~1, sin(f)+1 = 0~2
  f=f+0.05;
  fill(0,255,0);
  rect(0 , 0, 80, 80); //draw squad
  fill(255,0,255);
  ellipse(0, 0, 80, 80);
}
```
