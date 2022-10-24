# Flood Fill Algorithm

## Code

{% code overflow="wrap" %}
```c
#include<stdio.h>               # Library for Std Input-Output
#include<graphics.h>
#include<dos.h>
#include<conio.h>

void floodFill4(int x, int y, int newColor, int oldColor){
    if(getpixel(x,y) == oldColor){
        delay(5);
        putpixel(x, y, newColor);
        floodFill4(x+1, y, newColor, oldColor);
        floodFill4(x, y+1, newColor, oldColor);
        floodFill4(x-1, y, newColor, oldColor);
        floodFill4(x, y-1, newColor, oldColor);
    }
}

void floodFill8(int x, int y, int newColor, int oldColor){
    if(getpixel(x,y) == oldColor){
        delay(5);
        putpixel(x, y, newColor);
        floodFill8(x+1, y-1, newColor, oldColor);
        floodFill8(x+1, y, newColor, oldColor);
        floodFill8(x+1, y+1, newColor, oldColor);
        floodFill8(x, y+1, newColor, oldColor);
        floodFill8(x-1, y+1, newColor, oldColor);
        floodFill8(x-1, y, newColor, oldColor);
        floodFill8(x-1, y-1, newColor, oldColor);
        floodFill8(x, y-1, newColor, oldColor);
    }
}

int main(){
    int gDriver=DETECT, gMode, xc, yc, radius;
    initgraph(&gDriver, &gMode, "C:\\TURBOC3\\BGI");
    
    printf("\nFlood Fill Algorithm");
    printf("\n\nFirst Square filled by 4 connected approach");
    rectangle(150, 250, 200, 300);
    floodFill4(175, 275, 7, 0);
    
    printf("\n\nNext Square filled by 8 connected approach");
    rectangle(300, 250, 350, 300);
    floodFill8(325, 275, 9, 0);
  
    closegraph();
    return 0;
}

```
{% endcode %}

<figure><img src="../.gitbook/assets/Screenshot (2304).png" alt=""><figcaption></figcaption></figure>
