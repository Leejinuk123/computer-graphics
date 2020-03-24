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
