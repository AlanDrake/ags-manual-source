## `VideoPlayer` functions and properties

### `VideoPlayer.Open`

```ags
static VideoPlayer* VideoPlayer.Open(const string filename, bool autoPlay=true, RepeatStyle=eOnce)
```

Returns a VideoPlayer instance from a video file

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4", true, eOnce);
if (video != null)
{
  Overlay* screen = Overlay.CreateGraphical(0, 0, video.Graphic);
  while (video.State == ePlaybackOn)
  {
    Wait(1);
  }
  screen.Remove();
}
```

will open a video file and start playing it right away, show it on a screen overlay, wait until the playback is over, and then remove the overlay.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.Play`

```ags
VideoPlayer.Play()
```

Starts or resumes the playback.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4", false);
if (video != null)
{
  Overlay* screen = Overlay.CreateGraphical(0, 0, video.Graphic);
  video.Play();
}
```

will open a video file without starting it, show it on a screen overlay, and then begin the playback.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.Pause`

```ags
VideoPlayer.Pause()
```

Pauses the playback.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4");
Wait(80);
video.Pause();
```

will play a video for two seconds (at 40 game ticks per second) and then pause it.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.NextFrame`

```ags
VideoPlayer.NextFrame()
```

Advances video by 1 frame, may be called when the video is paused.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4", false);
video.NextFrame();
video.NextFrame();
Display("The video is now at the frame %d.", video.Frame);
```

will open a video without playing it and advance it by two frames.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.SeekFrame`

```ags
int VideoPlayer.SeekFrame(int frame)
```

Changes playback to continue from the specified frame; returns new position or -1 on error.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4");
if (video.SeekFrame(video.FrameCount / 2) == -1)
{
  Display("Could not seek to the middle of the video.");
}
```

will make the video continue from its middle frame, and report if that did not work.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.SeekMs`

```ags
int VideoPlayer.SeekMs(int position)
```

Changes playback to continue from the specified position in milliseconds; returns new position or -1 on error.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4");
if (video.SeekMs(5000) == -1)
{
  Display("Could not seek to the 5th second of the video.");
}
```

will make the video continue from the position of 5 seconds, and report if that did not work.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.Stop`

```ags
VideoPlayer.Stop()
```

Stops the video completely.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4");
Wait(80);
video.Stop();
```

will play a video for two seconds (at 40 game ticks per second) and then stop it completely.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.Frame`

```ags
readonly int VideoPlayer.Frame
```

Gets current frame index.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4");
Wait(40);
Display("The video is at the frame %d of %d.", video.Frame, video.FrameCount);
```

will play a video for one second and then tell which frame it has reached.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.FrameCount`

```ags
readonly int VideoPlayer.FrameCount
```

Gets total number of frames in this video.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4", false);
Display("The video has %d frames.", video.FrameCount);
```

will display the total number of frames in the video.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.FrameRate`

```ags
readonly float VideoPlayer.FrameRate
```

Gets this video's framerate (number of frames per second).

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4", false);
Display("The video runs at %.1f frames per second.", video.FrameRate);
```

will display the frame rate of the video.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.Graphic`

```ags
readonly int VideoPlayer.Graphic
```

Gets the number of sprite this video renders to.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4");
btnVideo.NormalGraphic = video.Graphic;
```

will play a video and show it on the button btnVideo, using the sprite that the video renders to.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.LengthMs`

```ags
readonly int VideoPlayer.LengthMs
```

The length of the currently playing video, in milliseconds.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4", false);
Display("The video is %d seconds long.", video.LengthMs / 1000);
```

will display the length of the video in seconds.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.Looping`

```ags
bool VideoPlayer.Looping
```

Gets/sets whether the video should loop.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4");
video.Looping = true;
```

will make the video start over each time it reaches the end.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.PositionMs`

```ags
readonly int VideoPlayer.PositionMs
```

The current playback position, in milliseconds.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4");
Wait(40);
Display("The video is at %d ms of %d ms.", video.PositionMs, video.LengthMs);
```

will play a video for one second and then tell the position it has reached, in milliseconds.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.Speed`

```ags
float VideoPlayer.Speed
```

The speed of playing (1.0 is default).

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4");
video.Speed = 2.0;
```

will play the video at twice the normal speed.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---

### `VideoPlayer.State`

```ags
readonly PlaybackState VideoPlayer.State
```

Gets the current playback state (playing, paused, etc).

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4");
Wait(40);
video.Pause();
if (video.State == ePlaybackPaused)
{
  Display("The video is paused.");
}
```

will pause a video after one second and confirm that its state is "paused".

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

*See also:* [`PlaybackState`](StandardEnums#playbackstate)

---

### `VideoPlayer.Volume`

```ags
int VideoPlayer.Volume
```

The volume of this video's sound, from 0 to 100.

Example:

```ags
VideoPlayer* video = VideoPlayer.Open("$DATA$/intro.mp4");
video.Volume = 50;
```

will play the video at half of its volume.

*Compatibility:* Supported by **AGS 4.0.0** and later versions.

---
