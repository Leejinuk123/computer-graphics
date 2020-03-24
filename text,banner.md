> ## 1. 프로세싱 배너 만들기(text 사용) : 
## 핵심 Keywords 
    text : 글자를 그래픽화 해준다.
    textSize : 글자의 크기를 정해준다.
    
* 참고 ctrl + t를 하면 자동으로 코드를 정렬해준다.
    
* * *

## 예제 1 : 
```processing
void setup() {
  size(800, 300);
  textSize(128);
}
int i=0;
void draw() {
  background(128);
  text("andong", i++, 200); //text print ctrl + t auto
  if(i>800) i=0;
}
```

![주석 2020-03-24 122457](https://user-images.githubusercontent.com/50895677/77385091-7dd2a680-6dca-11ea-96ff-16276ec65d5f.png)

* * *

> ## 1. 프로세싱 배너 만들기(키보드로 속도 조절하기) : 
## 핵심 Keywords 


* * *

## 예제 1 : 
```processing
void setup() {
  size(800, 300);
  textSize(128);
}
int i=0;
int a=1;
void draw() {
  background(0,255,0);
  text("andong", i+=a, 200); //text print ctrl + t auto
  if(i>800) i=0;
}
void keyPressed(){
  a = key-'0'; //key from ascii 숫자 바꾸기
}
```

## 예제 2(void keyPressed()를 빼고 if문으로 draw에 삽입한 예제) : 
```processing
void setup() {
  size(800, 300);
  textSize(128);
}
int i=0;
int a=1;
void draw() {
  background(0,255,0);
  if(keyPressed) //void keyPressed()를 빼고 if문으로 draw에 삽입한 예제
    a = key-'0';
  text("andong", i+=a, 200); //text print ctrl + t auto
  if(i>800) i=0;
}
/*void keyPressed(){
  a = key-'0'; //key from ascii
}*/
```

![주석 2020-03-24 123235](https://user-images.githubusercontent.com/50895677/77385498-9a231300-6dcb-11ea-96ba-df1bbe513200.png)
