# Bluetooth

---

Provide api allow user to set name, pin code for bluetooth.

> [!NOTE] 
> This feature is available on DUELink Spider only.

- **Bluetooth.SetName(name)** - Sets bluetooth name <br>
**name:**  Bluetooth name, max characters is 12. Default is "DUELink"

- **Bluetooth.SetPinCode(code)** - Sets bluetooth pin code  <br>
**code:** In text, has to be 4 characters from 0 to 9. Default is "1234"

The example below will change Bluetooth name to "DUELink00", and change pin code to "5678"

## [Python](#tab/py)
```py
duelink.Bluetooth.SetName("DUELink00")
duelink.Bluetooth.SetPinCode("5678")
```

## [JavaScript](#tab/js)
```js
await duelink.Bluetooth.SetName("DUELink00")
await duelink.Bluetooth.SetPinCode("5678")
```

## [.NET](#tab/net)
```cs
duelink.Bluetooth.SetName("DUELink00");
duelink.Bluetooth.SetPinCode("5678");
```

---