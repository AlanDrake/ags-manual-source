## `Walkbehind` functions and properties

### `Walkbehind.GetAtScreenXY`

```ags
static Walkbehind* Walkbehind.GetAtScreenXY(int x, int y)
```

Gets the walk-behind at the specified position on the screen.

Example:

```ags
Walkbehind *wb = Walkbehind.GetAtScreenXY(mouse.x, mouse.y);
if (wb != null)
{
  Display("The mouse is over walk-behind %d.", wb.ID);
}
```

will tell which walk-behind area, if any, is under the mouse cursor.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Walkbehind.GetAtRoomXY`

```ags
static Walkbehind* Walkbehind.GetAtRoomXY(int x, int y)
```

Returns the walk-behind at the specified position within this room.

Example:

```ags
Walkbehind *wb = Walkbehind.GetAtRoomXY(player.x, player.y);
if (wb != null)
{
  Display("The player stands on walk-behind %d.", wb.ID);
}
```

will tell which walk-behind area, if any, covers the player character's position in the room.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Walkbehind.GetDrawingSurface`

```ags
static DrawingSurface* Walkbehind.GetDrawingSurface()
```

Gets the drawing surface for the 8-bit walk-behind mask

Example:

```ags
DrawingSurface *surface = Walkbehind.GetDrawingSurface();
surface.DrawingColor = 1;
surface.DrawRectangle(10, 10, 50, 50);
surface.Release();
```

will draw a rectangle of walk-behind 1 onto the walk-behind mask.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

*See also:* [DrawingSurface](DrawingSurface)

---

### `Walkbehind.ID`

```ags
readonly int Walkbehind.ID
```

Gets the ID number for this walk-behind.

Example:

```ags
Walkbehind *wb = Walkbehind.GetAtRoomXY(player.x, player.y);
if (wb != null)
{
  Display("The player stands on walk-behind %d.", wb.ID);
}
```

will display the ID number of the walk-behind under the player character.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `Walkbehind.Baseline`

```ags
int Walkbehind.Baseline
```

Gets/sets this walk-behind's baseline.

Example:

```ags
Walkbehind *wb = Walkbehind.GetAtRoomXY(150, 100);
if (wb != null)
{
  wb.Baseline = 120;
}
```

will set the baseline of the walk-behind found at room position 150,100 to 120.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---
