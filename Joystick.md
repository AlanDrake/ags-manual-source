## `Joystick` functions and properties

### `Joystick.JoystickCount`

```ags
static readonly int Joystick.JoystickCount
```

Gets number of connected joysticks.

Example:

```ags
Display("%d joysticks are connected.", Joystick.JoystickCount);
```

will display the number of connected joysticks.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Joystick.Joysticks`

```ags
static readonly Joystick* Joystick.Joysticks[]
```

Gets a connected joystick by index or null on invalid index.

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null)
{
  Display("The first joystick is '%s'.", joy.Name);
}
```

will tell the name of the first connected joystick, if there is one.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Joystick.Name`

```ags
readonly String Joystick.Name
```

Gets joystick name

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null)
{
  Display("The first joystick is '%s'.", joy.Name);
}
```

will tell the name of the first connected joystick, if there is one.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Joystick.IsConnected`

```ags
readonly bool Joystick.IsConnected
```

Checks if joystick is really connected

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null && joy.IsConnected)
{
  Display("The first joystick is connected.");
}
```

will confirm that the first joystick is really connected.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Joystick.IsGamepad`

```ags
readonly bool Joystick.IsGamepad
```

Checks if joystick is a valid gamepad

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null && joy.IsGamepad)
{
  Display("The first joystick is a gamepad.");
}
```

will tell if the first joystick is a valid gamepad.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Joystick.IsGamepadButtonDown`

```ags
bool Joystick.IsGamepadButtonDown(eGamepad_Button button)
```

Checks if a gamepad button is pressed, including dpad.

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null && joy.IsGamepad && joy.IsGamepadButtonDown(eGamepad_ButtonA))
{
  Display("The A button is pressed.");
}
```

will tell if the A button of the first gamepad is currently pressed.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

*See also:* [`eGamepad_Button`](StandardEnums#egamepad_button)

---

### `Joystick.GetGamepadAxis`

```ags
float Joystick.GetGamepadAxis(eGamepad_Axis axis, optional float dead_zone);
```

Gets gamepad axis or trigger, trigger only has positive values.

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null && joy.IsGamepad)
{
  float x = joy.GetGamepadAxis(eGamepad_AxisLeftX, 0.2);
  if (x > 0.0)
  {
    Display("The left stick is pushed to the right.");
  }
}
```

will read the horizontal position of the left stick of the first gamepad, ignoring the small movements within the dead zone of 0.2, and tell if it is pushed to the right.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

*See also:* [`eGamepad_Axis`](StandardEnums#egamepad_axis)

---

### `Joystick.GetAxis`

```ags
float Joystick.GetAxis(int axis, optional float dead_zone)
```

Gets joystick axis or trigger, by index

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null && joy.AxisCount > 0)
{
  Display("The axis 0 is at %.2f.", joy.GetAxis(0, 0.2));
}
```

will display the position of the first axis of the first joystick, ignoring the small movements within the dead zone of 0.2.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Joystick.IsButtonDown`

```ags
bool Joystick.IsButtonDown(int button)
```

Checks if a joystick button is pressed.

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null && joy.IsButtonDown(0))
{
  Display("The first button is pressed.");
}
```

will tell if the first button of the first joystick is currently pressed.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Joystick.GetHat`

```ags
eJoystick_Hat Joystick.Joystick.GetHat(int hat)
```

Gets the direction a dpad from the joystick is pointing to.

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null && joy.HatCount > 0 && joy.GetHat(0) == eJoystick_HatUp)
{
  Display("The hat is pointing up.");
}
```

will tell if the first hat of the first joystick is pointing up.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

*See also:* [`eJoystick_Hat`](StandardEnums#ejoystick_hat)

---

### `Joystick.AxisCount`

```ags
readonly int Joystick.AxisCount
```

Gets axis count from the joystick

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null)
{
  Display("The joystick has %d axes.", joy.AxisCount);
}
```

will display the number of axes of the first joystick.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Joystick.ButtonCount`

```ags
readonly int Joystick.ButtonCount
```

Gets button count from the joystick

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null)
{
  Display("The joystick has %d buttons.", joy.ButtonCount);
}
```

will display the number of buttons of the first joystick.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Joystick.HatCount`

```ags
readonly int Joystick.HatCount
```

Gets hat count from the joystick

Example:

```ags
Joystick *joy = Joystick.Joysticks[0];
if (joy != null)
{
  Display("The joystick has %d hats.", joy.HatCount);
}
```

will display the number of hats of the first joystick.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.