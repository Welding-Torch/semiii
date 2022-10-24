# Boundary Fill Algorithm

## Code

{% code overflow="wrap" %}
```c
#include<stdio.h>             // Standard Library for input-output functions 
#include<graphics.h>          // Library for Graphic Functions
#include<dos.h>               // contains delay function
#include<conio.h>             // For console input-output


void boundaryFill4(int x, int y, int fillColor, int bColor){    // Function uses 4-connected approach 
    if(getpixel(x,y)!=bColor && getpixel(x,y)!=fillColor){      // If current pixel as not same as Boundary-Color and Fill-Color
        delay(5);                                               // Used for visualization of output
        putpixel(x, y, fillColor);                              // Put pixel at (x, y) coordinate with Fill-color
        boundaryFill4(x+1, y, fillColor, bColor);               // Recursively calling the functions
        boundaryFill4(x, y+1, fillColor, bColor);
        boundaryFill4(x-1, y, fillColor, bColor);               
        boundaryFill4(x, y-1, fillColor, bColor);
    }
}

void boundaryFill8(int x, int y, int fillColor, int bColor){
    if(getpixel(x,y)!=bColor && getpixel(x,y)!=fillColor){
        delay(5);
        putpixel(x, y, fillColor);
        boundaryFill8(x+1, y-1, fillColor, bColor);
        boundaryFill8(x+1, y, fillColor, bColor);
        boundaryFill8(x+1, y+1, fillColor, bColor);
        boundaryFill8(x, y+1, fillColor, bColor);
        boundaryFill8(x-1, y+1, fillColor, bColor);
        boundaryFill8(x-1, y, fillColor, bColor);
        boundaryFill8(x-1, y-1, fillColor, bColor);
        boundaryFill8(x, y-1, fillColor, bColor);
    }
}


int main(){
    int gDriver=DETECT, gMode, xc, yc, radius;
    initgraph(&gDriver, &gMode, "C:\\TURBOC3\\BGI");

    printf("\nBoundary Fill Algorithm");

    printf("\n\nFirst Square filled by 4 connected approach");
    rectangle(100, 150, 150, 200);
    boundaryFill4(125, 175, 7, 15);

    printf("\n\nNext Square filled by 8 connected approach");
    rectangle(250, 150, 300, 200);
    boundaryFill8(275, 175, 9, 15);

    closegraph();
    return 0;
}
```
{% endcode %}

## Output

<figure><img src="../.gitbook/assets/Screenshot (2303).png" alt=""><figcaption></figcaption></figure>
