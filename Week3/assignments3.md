What is Logspace and what is main difference with sRGB, why and when we use?
================


Linear versus sRGB
-----


In a linear color-space, the relationship between the stored numbers and the values they represent is a linear 1:1 ratio. 


This means that, for example, if you double the number, you double the intensity.


That sounds really easy, but the problem is that the human eye sensitivity to light is much finer at lower intensities than at high intensities. 


In particular, if we're using 8 bits to represent values (which means a total of 256 shades), we'll end up with too many light shades, and not enough dark shades (figure 1).


![linear](https://raw.githubusercontent.com/PhoebeLimm/2DDigitalCompositing/master/Week3/img/image00.jpg)


Thus, while a linear space makes perfect sense to use for computer processing, it is not suitable for human viewing because our eyes expect to see about the same amount of brightness change in between equal intervals. 


For example, our brain expects to see shade 32 twice as bright as 16, and shade 48 (which equals 32+16) twice as bright as 32.


To address this problem, most modern monitors apply a transformation called sRGB, a standard which uses a gamma curve to make the colors non-linear (figure 2).


The curve is shallower at the bottom, so it can display more dark values, and steeper at the top, so it can have fewer light values.


![sRGB](https://raw.githubusercontent.com/PhoebeLimm/2DDigitalCompositing/master/Week3/img/image02.jpg)


Log (short for logarithmic)
---------
You can think of log as a color space “archiver” (in the same way zip or rar does it for files). 


This is because, while linear space increments values in equal steps, a logarithmic color space compresses the values in the white and black areas of an image, thus minimizing the space required to store the information (figure 4).


![Log](https://raw.githubusercontent.com/PhoebeLimm/2DDigitalCompositing/master/Week3/img/image01.jpg)

As a side effect, this format also allows us to paint in more manageable formats such as 16 bit .tif; This is because, if you follow the above analogy, a 16 bit log file can “unarchive” to a 32bit linear format without clipping.


The most common log formats that you will encounter are ARRI Log and Cineon Dpx.


Log vs. Linear Color Space
----


![vs](https://raw.githubusercontent.com/PhoebeLimm/2DDigitalCompositing/master/Week3/img/Log-Curve.jpg)

Above is a (not necessarily exact) representation of the differences between **a linear color curve and a Log color curve.**


If you’re familiar with  curves, you know that the bottom left of the curve represents your blacks and shadows, and as you move to the top right of the curve, you have your **highlights and whites.**


As you can see, a Log curve pushes the darker part of the image upwards to retain shadows. 


The top of the curve **shifts down to retain highlights.** Therefore, you retain more data from each side of the color curve.




Linear color space has **constant and unchanged luminance values** true to their exact mathematical values in the scene. 


To the human eye, this will look very dark and muddy in certain areas and overexposed in others because our eyes (and monitors for that matter) see colors differently than their exact luminance values and can see more detail in bright and dark areas. 


Therefore, we have to apply a different color space in order to see the color information in a more aesthetically pleasing way, as well as standardize color values for displays and monitors.



출처 : 


- https://www.artstation.com/tiberius-viris/blog/3ZBO/color-space-management-srgb-linear-and-log


- https://www.rocketstock.com/blog/tips-for-log-color-space-compositing/

