
# pingdicate

> get visual indication of average latency to host(s) in your menu bar

##### install

ensure you've got a copy of [anybar](https://github.com/tonsky/AnyBar) in your `/Applications` directory, then...

```bash
npm install --global pingdicate
```

as a `postinstall` script, pingdicate's `plist` configuration file will be moved to `~/Library/LaunchAgents` and loaded into `launchctl`. it specifes some default host addresses which you will likely want to override.

to change the host addresses or to specify a path to anybar other than `/Applications/AnyBar.app`, open `~/Library/LaunchAgents/re.gitigno.pingdicate.plist` in a text editor and modify the ip address arguments to the `-h` option in the `ProgramArguments` string section of the file.

if your path to anybar differs from the expected default, add `-a /path/to/your/anybar` in the `ProgramArguments` string.

to apply your changes, run `launchctl stop re.gitigno.pingdicate.plist && launchctl unload re.gitigno.pingdicate && launchctl load re.gitigno.pingdicate` to stop, reload and restart the service.

##### uninstall

```bash
launchctl stop re.gitigno.pingdicate && launchctl unload re.gitigno.pingdicate && mv ~/Library/LaunchAgents/re.gitigno.pingdicate.plist ~/.Trash/
```

to stop, unload and delete the service from `launchctl`.
