
### Mention the name of Programming language and Graphics Library you  are using this semester for performing your Computer Graphics Lab and Project

#### Programming Language to be used: Python
#### Libraries: PIL, math, Matplotlib

### Write the code snippets for setting graphics environment  in your chosen graphics library and display the resolution of your display system through functions/classes provided by your graphics library.


```python
import ctypes
user32 = ctypes.windll.user32
user32.SetProcessDPIAware()
height, width = user32.GetSystemMetrics(0), user32.GetSystemMetrics(1)
print(f'Resolution is: {height} x {width}')
```

    Resolution is: 1920 x 1080
    

### Get Familiar with the coordinate system and Draw a flag of Nepal using the chosen Graphics geometrical functions/ classes provided by the your chosen graphics library and also color the flag accordingly.


```python
from PIL import Image, ImageDraw
from math import*

from IPython.display import display

I ,k, l, m, n, o, _=Image.new('P', (394, 480)), 479, 180, 465, 232, 347, 255;
D=ImageDraw.Draw(I);
P, G=D.polygon, D.pieslice
I.putpalette([_, _, _, 0, 0, _, _, 20, 60])

def S(x, y, r, e, l, b):
    p, a, h=[], 2*pi/e, r*l
    c, d=[0, -a/2][b], [a/2, 0][b]
    for i in range(e):
        p+=[(x+r*cos(i*a+c), y+r*sin(i*a+c)), (x+h*cos(i*a+d), y+h*sin(i*a+d))]
    P(p, fill=0)

P([(0, 0), (393, 246), (144, 246), (375, k), (0, k)], fill=1) #outer polygon with blue color
P([(14, 25), (o, n), (110, n), (o, m), (14, m)], fill=2) # inner polygon with red color over blue polygon 
S(96, o, 68, 12, .6, 0) #Sun Shape at lower part
G([(31, 90), (163, 221)],0 ,l , fill=0) #Semi cricle for the moon
G([(28, 68), (166, 200)],0 ,l , fill=2) #another smaller semicircle with red color over the provious semicircle to make it small
S(96, 178, 40, 16, .7, 1) #Sun shape above the moon semicicle

display(I)
```


![png](output_5_0.png)



```python

```
