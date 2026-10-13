## `WalkableArea` functions and properties

### `WalkableArea.GetAtScreenXY`

```ags
static WalkableArea* WalkableArea.GetAtScreenXY(int x, int y)
```

Gets the walkable area at the specified position on the screen.

Example:

```ags
WalkableArea *area = WalkableArea.GetAtScreenXY(mouse.x, mouse.y);
if (area != null)
{
  Display("The mouse is over walkable area %d.", area.ID);
}
```

will tell which walkable area, if any, is under the mouse cursor.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.GetAtRoomXY`

```ags
static WalkableArea* WalkableArea.GetAtRoomXY(int x, int y)
```

Returns the walkable area at the specified position within this room.

Example:

```ags
WalkableArea *area = WalkableArea.GetAtRoomXY(player.x, player.y);
if (area != null)
{
  Display("The player stands on walkable area %d.", area.ID);
}
```

will tell which walkable area, if any, the player character is standing on.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.GetDrawingSurface`

```ags
static DrawingSurface* GetDrawingSurface()
```

Gets the drawing surface for the 8-bit walkable mask

Example:

```ags
DrawingSurface *surface = WalkableArea.GetDrawingSurface();
surface.DrawingColor = 1;
surface.DrawRectangle(10, 10, 50, 50);
surface.Release();
```

will draw a rectangle of walkable area 1 onto the walkable mask.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.SetScaling`

```ags
void WalkableArea.SetScaling(int min, int max)
```

Changes this walkable area's scaling level.

Example:

```ags
WalkableArea.GetAtRoomXY(100, 150).SetScaling(50, 100);
```

will make the walkable area found at the room position 100,150 scale characters from 50% to 100% of their normal size.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.GetProperty`

```ags
int WalkableArea.GetProperty(const string property)
```

Gets an integer custom property for this area.

Example:

```ags
if (Room.WalkableAreas[1].GetProperty("Slippery") > 0)
{
  Display("Careful, it's slippery here!");
}
```

will print the message if the walkable area 1 has its "Slippery" property set to more than 0.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.GetTextProperty`

```ags
String WalkableArea.GetTextProperty(const string property)
```

Gets a text custom property for this area.

Example:

```ags
String sound = Room.WalkableAreas[1].GetTextProperty("StepSound");
Display("This area uses the step sound '%s'.", sound);
```

will display the value of the "StepSound" text property of the walkable area 1.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.SetProperty`

```ags
bool WalkableArea.SetProperty(const string property, int value)
```

Sets an integer custom property for this area.

Example:

```ags
Room.WalkableAreas[1].SetProperty("Slippery", 1);
```

will set the "Slippery" property of the walkable area 1 to 1.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.SetTextProperty`

```ags
bool WalkableArea.SetTextProperty(const string property, const string value)
```

Sets a text custom property for this area.

Example:

```ags
Room.WalkableAreas[1].SetTextProperty("StepSound", "gravel");
```

will set the "StepSound" text property of the walkable area 1 to "gravel".

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.ID`

```ags
readonly int WalkableArea.ID
```

Gets the ID number for this area.

Example:

```ags
WalkableArea *area = WalkableArea.GetAtRoomXY(player.x, player.y);
if (area != null)
{
  Display("The player stands on walkable area %d.", area.ID);
}
```

will display the ID number of the walkable area the player character is standing on.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.Enabled`

```ags
bool WalkableArea.Enabled
```

Gets/sets whether this walkable area is enabled.

Example:

```ags
Room.WalkableAreas[2].Enabled = false;
```

will disable the walkable area 2, so that characters can no longer walk on it.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.ScalingMin`

```ags
readonly int WalkableArea.ScalingMin
```

Gets this walkable area's minimal scaling level.

Example:

```ags
WalkableArea *area = Room.WalkableAreas[1];
Display("The area scales characters from %d to %d percent.", area.ScalingMin, area.ScalingMax);
```

will display the minimal and maximal scaling levels of the walkable area 1.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.ScalingMax`

```ags
readonly int WalkableArea.ScalingMax
```

Gets this walkable area's maximal scaling level.

Example:

```ags
WalkableArea *area = Room.WalkableAreas[1];
Display("The area scales characters from %d to %d percent.", area.ScalingMin, area.ScalingMax);
```

will display the minimal and maximal scaling levels of the walkable area 1.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `WalkableArea.FaceDirectionRatio`

```ags
static float WalkableArea.FaceDirectionRatio
```

Gets/sets the optional y/x ratio of character's facing directions, determining directional loop selection for each Character while on this area.

Example:

```ags
Room.WalkableAreas[1].FaceDirectionRatio = 1.5;
```

will set the y/x ratio that characters use to select their directional loops while standing on the walkable area 1 to 1.5.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---
