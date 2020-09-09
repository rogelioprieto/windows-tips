## How to change window title bar size in Windows 10 

## Problem: 
Window title bar is so small but Windows 10 interface doesn't have an option to increase title bar size.

We need to change this:
![https://i.stack.imgur.com/CQj6Y.png](https://i.stack.imgur.com/CQj6Y.png)


## Solution:
1. Change the registry at ```HKEY_CURRENT_USER\Control Panel\Desktop\WindowMetrics```.

2. For ```CaptionHeight``` and ```CaptionWidth```, use the following formula: ```-15*desired height in pixels```.  
For example, to set the title bar height to ```18px```, set the ```CaptionHeight``` value to ```-15*18```, resulting in ```-270```.

I recommend set ```-405```.  I got this value from: ```-15*27=405```.


3. (optional). I you want to increase  


## Source:  
<https://superuser.com/questions/952395/how-to-change-window-title-bar-size-in-windows-10>
