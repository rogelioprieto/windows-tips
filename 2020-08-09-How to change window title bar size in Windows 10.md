## How to change window title bar size in Windows 10 

## Problem: 
Window title bar is so small but Windows 10 interface doesn't have an option to increase title bar size.

We need to change this:  
![https://i.stack.imgur.com/CQj6Y.png](https://i.stack.imgur.com/CQj6Y.png)


## Solution:

1. Open Windows registry, press ```Windows key + R``` and type ```regedit```
1. Change the registry at  
```HKEY_CURRENT_USER\Control Panel\Desktop\WindowMetrics```.

2. Set this values:
For ```CaptionWidth``` set ```-405```.

For ```CaptionHeight``` set ```-405```.

**Explanation:**
The metrics used is *Twip* (abbreviated from "twentieth of a point") defined as 1/20 of a typographical point. For ```CaptionHeight``` and ```CaptionWidth```, use the following formula: ```-15*desired height in pixels```.  
For example, to set the title bar height to ```18px```, set the ```CaptionHeight``` value to ```-15*18```, resulting in ```-270```.

I recommend set ```-405```.  I got this value using ```27px``` size: ```-15*27=405```.


3. (optional). I you want to increase ```ScrollWidth``` set value to ```-330```. I got this value using ```22px``` size.


RPA-TODO--------DELETE THIS:
and ```ScrollHeight```.




## Source:  
<https://superuser.com/questions/952395/how-to-change-window-title-bar-size-in-windows-10>

## Notes:
Twips are screen-independent units to ensure that the proportion of screen elements are the same on all display systems. A twip is defined as being 1/1440 of an inch (approximately 0.0176 mm). Reference: <https://en.wikipedia.org/wiki/Twip>
