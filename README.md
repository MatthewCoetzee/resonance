Resonance
====
Resonance is flutter volume controller and vibration plugin

![](static/resonance.png)

Features
-----
- Get current volume level
- Get max volume level
- Set volume level
- Set max volume level
- Set mute volume level
- Showing volume UI (Android only)
- Volume stream types (music, notification, alarm, etc.)
- Listenable volume level

Usage
-----

Get current volume level

```dart
/// [streamType] by the default is set to [StreamType.music]
var crntVol = await Resonance.getCurrentVolumeLevel(streamType: StreamType.alarm);
print(crntVol);
```

Set volume level

```dart
/// [showVolumeUI] by the default is set to false
var crntVol = await Resonance.setVolumeLevel(0.5, showVolumeUI: true);
print(crntVol);
```

Listener

```dart
@override
void initState() {
    super.initState();
    /// Add listener
    Resonance().addListener((volume) {
        setState(() {
            _volumeLevel = volume;
        });
    });
}

@override
void dispose() {
    /// Don't forget to use [removeListener] after
    Resonance().removeListener();
    super.dispose();
}
```

Status
------
Version 0.0.1 is under development

Note
------
Currently, the plugin only available for Android.
Pull requests and contributors are welcome.

Developer
------
```
Tegar Bangun Suganda
```

[@canaryv8][2] (Twitter)\
[@suganda8][3] (Github)

License
-------
```
MIT License

Copyright (c) 2022 Tegar Bangun Suganda (ASTARIA)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

[2]: https://twitter.com/canaryv8
[3]: https://github.com/suganda8