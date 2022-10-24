---
description: Run this in TurboC
---

# Bezier Curve

## Code

{% code overflow="wrap" %}
```c
#include<stdio.h>
#include<graphics.h>
#include<conio.h>
#include<math.h>

void main(){
    int x[100],y[100],i,n;
    double puty,putx,t;
    int gd=DETECT,gm;
    initgraph(&gd,&gm,"C:\\TURBOC3\\BGI");
    printf("\n****** Bezier Curve ***********");
    printf("\nEnter Number of Points: ");
    scanf("%d",&n);
    for ( i = 0; i < n; i++)
    {
	printf("Enter x and y coordinated of point %d: ",i+1);
	scanf("%d%d",&x[i],&y[i]);
	putpixel(x[i],y[i],3);
    }
    for(t=0.0;t<=1.0;t=t+0.001){
	putx=pow(1-t,3)*x[0]+ 3*t*pow(1-t,2)*x[1]+ 3*t*t*pow(1-t,1)*x[2]+ pow(t,3)*x[3];
	puty=pow(1-t,3)*y[0]+ 3*t*pow(1-t,2)*y[1]+ 3*t*t*pow(1-t,1)*y[2]+ pow(t,3)*y[3];
	putpixel(putx,puty,WHITE);
    }
    getch();
    closegraph();
}
```
{% endcode %}

## Output

<figure><img src="../.gitbook/assets/Screenshot (2302).png" alt=""><figcaption></figcaption></figure>
