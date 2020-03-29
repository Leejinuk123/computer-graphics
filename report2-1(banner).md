> ## 1. 움직이는 배너 만들기

* * * 
> 예제 : 
```processing
void setup() {
  size(800, 300);
  textSize(50);
}
int i=0;
int a=1;
void draw() {
  background(128);
  if (keyPressed)
    a = key-'0';
  text("Graphics", i=i+a, 150); //text print ctrl + t auto
  if(i>800) i=0;
}
```

![캡처](https://user-images.githubusercontent.com/50895677/77837077-be05a080-719f-11ea-8215-61c3adb7528f.PNG)
