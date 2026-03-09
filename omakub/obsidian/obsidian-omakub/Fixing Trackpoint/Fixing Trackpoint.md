
https://rabexc.org/posts/carbon-x1-trackpad

Custom libinput quirk file: 
```bash
/etc/libinput/local-overrides.quirks
```

```ini
[Elan TrackPoint Custom]
MatchName=Elan TrackPoint
MatchUdevType=pointingstick
AttrTrackpointMultiplier=2.5
AttrPressureRange=10:20
```

AttrTrackpointMultiplier : acceleration of point (higher is faster)
AttrPressureRange: pressure threshold (minimum:maximum)

To view currently applied: 
Elan trackpoint: event7
```bash
libinput quirks list /dev/input/event7
```


# Changes with Ubuntu 25

Trackpad moved to event 5, and AttrPressureRange is no longer an argument:

```
Device:                  Elan TrackPoint
Kernel:                  /dev/input/event5
Id:                      i2c:04f3:0020
Group:                   6
Seat:                    seat0, default
Capabilities:            pointer
```

