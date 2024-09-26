# Bluetooth

---

Provide api allow user to set name, pin code for bluetooth.


- **Bluetooth.SetName(name)** - Sets bluetooth name <br>
**name:**  Bluetooth name, max characters is 12. Default is "DUELink"
**Returns:** true = success, false = not success <br>

- **Bluetooth.SetPinCode(code)** - Sets bluetooth pin code  <br>
**code:** In "text", has to be 4 characters from 0 to 9. Default is "1234"
**Returns:** true = success, false = not success <br>

The example below will change Bluetooth name to "DUELink00", and change pin code to "5678"

## [Python](#tab/py)
```py
print(duelink.Bluetooth.SetName("DUELink00"))

time.sleep(5) # Delay few seconds for bluetooth reset

print(duelink.Bluetooth.SetPinCode("5678"))
```

## [JavaScript](#tab/js)
```js
console.log(await duelink.Bluetooth.SetName("DUELink00"))

await Util.sleep(5000) // Delay few seconds for bluetooth reset

console.log(await duelink.Bluetooth.SetPinCode("5678"))
```

## [.NET](#tab/net)
```cs
duelink.Bluetooth.SetName("DUELink00");

Thread.Sleep(5000)  // Delay few seconds for bluetooth reset

duelink.Bluetooth.SetPinCode("5678");
```

---