## `GameInfo` properties

GameInfo struct provides optional information about the game, which corresponds to the "Info" category section of the General Settings pane in the Editor.

*Compatibility:* Supported by **AGS 3.6.3** and later versions.

---

### `GameInfo.Title`

```ags
static readonly attribute String GameInfo.Title
```

Gets the game's title.

Example:

```ags
Display("Welcome to %s!", GameInfo.Title);
```

will display the game's title.

---

### `GameInfo.Description`

```ags
static readonly attribute String GameInfo.Description
```

Gets the game's description.

Example:

```ags
Display(GameInfo.Description);
```

will display the game's description.

---

### `GameInfo.DeveloperName`

```ags
static readonly attribute String GameInfo.DeveloperName
```

Gets the game's developer's name.

Example:

```ags
Display("Developed by %s.", GameInfo.DeveloperName);
```

will display the name of the game's developer.

---

### `GameInfo.DeveloperURL`

```ags
static readonly attribute String GameInfo.DeveloperURL
```

Gets the game's developer's URL string.

Example:

```ags
Display("Visit us at %s.", GameInfo.DeveloperURL);
```

will display the developer's web address.

---

### `GameInfo.Genre`

```ags
static readonly attribute String GameInfo.Genre
```

Gets the game's genre description.

Example:

```ags
Display("Genre: %s.", GameInfo.Genre);
```

will display the game's genre.

---

### `GameInfo.ReleaseDate`

```ags
static readonly attribute DateTime* GameInfo.ReleaseDate
```

Gets the game's release date as a DateTime instance.

Example:

```ags
DateTime *date = GameInfo.ReleaseDate;
Display("Released on %d/%d/%d.", date.DayOfMonth, date.Month, date.Year);
```

will display the game's release date.

---

### `GameInfo.Version`

```ags
static readonly attribute String GameInfo.Version
```

Gets the game's release version, represented as "X.Y.Z.W" string.

Example:

```ags
Display("Version %s", GameInfo.Version);
```

will display the game's version, such as "1.0.0.0".
