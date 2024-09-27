# Script

---

These methods allow developers to control DUE Scripts right from within Python, JavaScript or .NET

- **Script.New()** - Clears the program stored in flash <br>
- **Script.Load(script)** - Loads the line into internal buffer <br>
**script:** Line to load into internal buffer <br>
- **Script.Record()** - Sends the internal buffer to the device, overwriting any previous programs <br>
- **Script.Read()** - Read the program stored in flash and return as string <br>
- **Script.Execute(script)** - Executes the single line of code immediately <br>
**script:** Script to be executed<br>
- **Script.Run()** - Runs the program stored in flash  <br>

> [!NOTE]
> `Script.Run()` switches from immediate mode to run mode. Meaning, DUELink run by itself using the stored scripts in flash, no need host.



This example will check any script stored in flash, and clear them if program found.

## [Python](#tab/py)

```py

currentScript = duelink.Script.Read()

if (currentScript != ""):
    duelink.Script.New()
```

## [JavaScript](#tab/js)

```js
let currentScript = await duelink.Script.Read()

if (currentScript != "")
    await duelink.Script.New();
```

## [.NET](#tab/net)

```cs
var currentScript = duelink.Script.Read();

if (currentScript != "")
    duelink.Script.New();
```

---

This example will load a simple program line by line and then record it.

## [Python](#tab/py)

```py
duelink.Script.Load("c = 10")
duelink.Script.Load("@Blink")
duelink.Script.Load("Led(100,100,c)")
duelink.Script.Record()
```

## [JavaScript](#tab/js)

```js
await duelink.Script.Load("c = 10")
await duelink.Script.Load("@Blink")
await duelink.Script.Load("Led(100,100,c)")
await duelink.Script.Record()
```

## [.NET](#tab/net)

```cs
duelink.Script.Load("c = 10");
duelink.Script.Load("@Blink");
duelink.Script.Load("Led(100,100,c)");
duelink.Script.Record();
```

___

This is an example to execute a single line(immediate mode). This does not modify the application stored in flash. 


## [Python](#tab/py)

```py
duelink.Script.Execute("LED(200,200,10)")
```

## [JavaScript](#tab/js)

```js
await duelink.Script.Execute("LED(200,200,10)")
```

## [.NET](#tab/net)

```cs
duelink.Script.Execute("LED(200,200,10)");
```

___

You can also access a previously recorder program using goto (to label) or by calling a function that has a return. This example calls the recorded program above.

## [Python](#tab/py)

```py
duelink.Script.Execute("c=5:goto Blink")
```

## [JavaScript](#tab/js)

```js
await duelink.Script.Execute("c=5:goto Blink")
```

## [.NET](#tab/net)

```cs
duelink.Script.Execute("c=5:goto Blink");
```

___


 