> # 3개의 동그라미가 내려가는 그래픽

```processing
void setup(){
  size(500,500);
}
int i = 0;
void draw(){
 background(0);
 i=i+10;
 fill(255,0,0);
 ellipse(250,i,50,50);
 fill(0,255,0);
 ellipse(250-30,i,50,50);
 fill(0,0,255);
 ellipse(250-60,i,50,50);
 if(i>500) i = 0;
}
```

---

> #### Simulation

![2022-03-08-17-34-16](https://user-images.githubusercontent.com/50895677/157198637-bd10399a-3410-4342-9838-6d2568f969eb.gif)
