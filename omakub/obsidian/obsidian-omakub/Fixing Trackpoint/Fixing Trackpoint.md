
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
```

To view currently applied