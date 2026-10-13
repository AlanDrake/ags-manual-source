## `Touch` functions and properties

### `Touch.TouchPointerCount`

```ags
readonly static int Touch.TouchPointerCount
```

Number of touch pointers registered by the game engine.

Example:

```ags
Display("%d touch pointers are registered.", Touch.TouchPointerCount);
```

will display the number of touch pointers registered by the engine.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Touch.TouchPointers`

```ags
readonly static TouchPointer* Touch.TouchPointers[]
```

Accesses a touch pointer state by its identifier.

Example:

```ags
for (int i = 0; i < Touch.TouchPointerCount; i++)
{
  if (Touch.TouchPointers[i].IsDown)
  {
    Display("Pointer %d touches the screen.", Touch.TouchPointers[i].ID);
  }
}
```

will go through all the touch pointers and tell which of them are currently touching the screen.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

*See also:* [`TouchPointer`](TouchPointer)