
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
