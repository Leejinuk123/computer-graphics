> ## 1. 위에서 아래로 움직이는 배너 만들기(한글)
    키보드로 값을 읽어와서 움직이는 글자의 속도를 조절한다.

# 코드 : 
```processing
PFont f;
void setup() {
  size(800, 300);
  textSize(50);
  fill(0,255,0);
  f=createFont("굴림",64);
  textFont(f);
}
int i=0;
int a=1;
void draw() {
  background(128);
  if(keyPressed)
    a = key-'0';
  text("안동대 컴공 사랑합니다.", 60, i+=a); //text print ctrl + t auto
  if(i>300) i=0;
}
```

![캡2처](https://user-images.githubusercontent.com/50895677/77837352-476aa200-71a3-11ea-8f5a-d5cd94b98f04.PNG)


* * *
* * *
* * *

> ## 2. 작성 소감 : 
  직접 창작물을 만들어본 것 같아서 너무 재밌고 실제로 사이트 광고들이나 이런식으로 작동하는 배너를 본 것 같아 더 실감이 났던 활동이였습니다.
  특히 키보드로 속도를 조절하는 코드를 작성했을 때는 이런 그래픽과 사람이 상호작용을 할 수 있다는 것에 더욱 놀랐습니다.
