# mad015
basic rotate loop

![mad015](https://github.com/nicolasbaez/mad015/blob/master/mad015.gif)

```processing
float r1;
float j=0;
float rr;
float gg;
float bb;
void setup() {
  size(512, 256);
  background(255);
  noStroke();
}
void draw() {
  background(255);
  r1=map(sin(radians(j)), -1, 1, height*0.48, height*0.32);
  beginShape();
  fill(rr, gg, bb);
  for (float i=j; i<=360+j; i+=360/4) {
    float xx=r1*cos(radians(i))+width/2;
    float yy=r1*sin(radians(i))+height/2;
    vertex(xx, yy);
  }
  endShape();
  beginShape();
  fill(255);
  for (float i=j; i<=360+j; i+=360/4) {
    float xx=0.75*r1*cos(radians(i))+width/2;
    float yy=0.75*r1*sin(radians(i))+height/2;
    vertex(xx, yy);
  }
  endShape();
  rr=map(sin(radians(j)), -1, 1, 0, 256);
  gg=map(sin(radians(j)), -1, 1, 128, 128);
  bb=map(sin(radians(j)), -1, 1, 256, 0);
  j+=map(sin(radians(j)), -1, 1, 1, 4);
  if (j>=360&&j<=720) {
    saveFrame("gif/mad015-######.png");
  }
}
```
