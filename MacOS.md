## Mac OS


This is a little cheatsheet about [MacOS](https://en.wikipedia.org/wiki/MacOS).

### Change the name of machine
```
scutil --set ComputerName "MacBook Willy"
scutil --set HostName "centauri"
scutil --set LocalHostName "MacBookPro"
```
## How to see ao routes on my machine
```
netstat -nr
```

## Flush DNS
```
sudo killall -HUP mDNSResponder
```
