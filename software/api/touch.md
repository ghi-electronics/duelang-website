# Touch

This feature allows sensing of a finger or human touch to a pin, or when using a touch screen, use 'x' or 'y' to return the x & y positions where the screen is being touched.

- **Touch.Read(pin)** - Initializes the pin for touch, or reads the x y position on a touch screen   <br>
**pin:** pin number, 'x', or 'y' <br>
**pin Returns:** 0 = pin not touched, 1 = pin touched <br>
**x or y Returns:**  -1 = screen not touched, x position , y position


This example detects human touch on pin 6, interval 100ms


### [Python](#tab/py)
```py
while True:
    touched = duelink.Touch.Read(6)

    if (touched):
        print("touched")
                
    time.sleep(0.1)

```

### [JavaScript](#tab/js)
```js
while (true)
{
    let touched = await duelink.Touch.Read(6)

    if (touched)
        console.log("touched")
                
    await Util.sleep(100)
}
```

### [.NET](#tab/net)
```cs
while (true)
{
    var touched = duelink.Touch.Read(6);

    if (touched)
        Console.WriteLine("touched");
                
    Thread.Sleep(100);
}
```

### [DUE Script](#tab/due)
```
@Loop
# Pin touch
a=TouchRead(0):b=TouchRead(1):c=TouchRead(2)
If a>0:PrintLn("pin 0"):End 
If b>0:PrintLn("pin 1"):End
If c>0:PrintLn("pin 2"):End 

# Prints x & y coordinates from touch screen to the Due Console Log window
x = TouchRead('x')
y = TouchRead('y')
LogLn(x)
LogLn(y)

Wait(100)
Goto Loop
```
---