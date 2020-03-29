> ## 1. 움직이는 배너 만들기

* * * 
> 예제 : 
```processing
void setup() {
  size(800, 300);
  textSize(50);
  fill(0,255,0);
}
int i=0;
int dir=1;
int a=1,sp=1;
void draw() {
  background(128);
  if (keyPressed)
    sp = key-'0';
  text("Graphics", i, 150); //text print ctrl + t auto
  if(i>800) dir=-1;
  if(i<0) dir=1;
  i=i+dir*sp;
}

```

![캡1처](https://user-images.githubusercontent.com/50895677/77837236-d37bca00-71a1-11ea-9391-1415fea446ad.PNG)

