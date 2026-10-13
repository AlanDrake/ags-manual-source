## `TouchPointer` functions and properties

### `TouchPointer.ID`

```ags
readonly int TouchPointer.ID
```

Gets this touch pointer's identifier.

Example:

```ags
TouchPointer *tp = Touch.TouchPointers[0];
Display("The first touch pointer has the ID %d.", tp.ID);
```

will display the identifier of the first touch pointer.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `TouchPointer.IsDown`

```ags
readonly bool TouchPointer.IsDown
```

Gets whether this touch pointer is currently down (in touching state).

Example:

```ags
if (Touch.TouchPointers[0].IsDown)
{
  Display("The screen is being touched.");
}
```

will print a message if the first touch pointer is currently touching the screen.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `TouchPointer.X`

```ags
readonly int TouchPointer.X
```

Gets this touch pointer's X screen coordinate.

Example:

```ags
TouchPointer *tp = Touch.TouchPointers[0];
if (tp.IsDown)
{
  Display("The touch is at %d,%d.", tp.X, tp.Y);
}
```

will display the screen coordinates of the first touch pointer while it is touching the screen.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `TouchPointer.Y`

```ags
readonly int TouchPointer.Y
```

Gets this touch pointer's Y screen coordinate.

Example:

```ags
TouchPointer *tp = Touch.TouchPointers[0];
if (tp.IsDown)
{
  Display("The touch is at %d,%d.", tp.X, tp.Y);
}
```

will display the screen coordinates of the first touch pointer while it is touching the screen.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.