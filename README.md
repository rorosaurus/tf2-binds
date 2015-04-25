# TF2binds

This is a mapping of custom keybinds for Team Fortress 2. Includes class-specific binds.

### Applying to TF2 on Windows
Copy the CustomBinds directory into this directory:  
```
C:\Program Files (x86)\Steam\SteamApps\common\Team Fortress 2\tf\custom
```
Then launch TF2.  

### How it works
TF2 parses your `~\tf\custom` folder for custom content (sounds, models, scripts, etc). Each subfolder in the `custom` directory represents an individual mod. In effect, CustomBinds is a mod for TF2's `~\tf\cfg\config.cfg`.

The subdirectory in `~\custom\CustomBinds\` is called `cfg`. This tells TF2 which content folder under `~\tf\` will be modified. In `~\custom\CustomBinds\cfg\`, you will find all the `*.cfg` files that modify TF2's default keybind configuration.

The file `autoexec.cfg` overrides `config.cfg` from `~\tf\cfg\`. You can put custom binds and scripts in `autoexec.cfg` to your liking. This will be a 'global' custom bind/script configuration that affects all classes. 

There are also `*.cfg` files for each individual class as well as possibly a few special scripts that are called by other ones. A special `reset.cfg` script exists for restoring global binds when changing between classes which have unique, class-specific binds.

Go to [r/TF2scripts](https://www.reddit.com/r/tf2scripts), the [teamfortress wiki](https://wiki.teamfortress.com/wiki/Scripting) or [google](https://www.google.com/) for guides and information on scripting.
