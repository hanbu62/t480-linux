
Used to prevent system from sleeping

Change made to shell config file

```bash
alias stayawake='systemd-inhibit --what=idle --who="Manual" --why="Staying awake"'
```

Usage: 
```bash
# stay awake for 4 hours
stayawake sleep 4h

# stay awake for 30 minutes
stayawake sleep 30m

# Run in background
stayawake sleep 4h &
```

Alias for ending "awake" sessions
```bash
alias killawake='pkill -f "systemd-inhibit.*sleep"'
```

Usage: 
```bash
killawake
```


Viewing all sleep sessions and ending specific ones
```bash
# view jobs
jobs

#kill job (e.g. #1)
kill %1
```