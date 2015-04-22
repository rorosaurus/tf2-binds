TF2binds
========
**A mapping of custom keybinds for Team Fortress 2. Includes class-specific binds.**

*Windows*:  
Copy the CustomBinds directory into this directory:  
```
C:\Program Files (x86)\Steam\SteamApps\common\Team Fortress 2\tf\custom
```
Then launch TF2.  

*How it works*:  
TF2 parses your `~\tf\custom` folder for custom content (sounds, models, scripts, etc). Each subfolder in the `custom` directory represents an individual mod. In effect, CustomBinds is a mod for TF2's `~\tf\config\config.cfg`.

The subdirectory in `~\custom\CustomBinds\` is called `scripts`. This tells TF2 which content folder under `~\tf\` will be modified. In `~\custom\CustomBinds\scripts\`, you will find all the `*.cfg` files that modify TF2's default keybind configuration.

`autoexec.cfg` should start out as a copy of the default `config.cfg` from `~\tf\config\`. From there, you can modify `autoexec.cfg` to your liking with all the binds you want to have. This will be a 'global' custom bind configuration that affects all classes.

You can also customize binds for individual classes to override the 'default' bind behavior set by `autoexec.cfg`. For example, if you want a special bind for the Medic class which announces to the team that you have an Ubercharge ready that you want to assign to the G key, you would create another `.cfg` file called `medic.cfg`.

```
// medic.cfg
bind g "say_team Ubercharge ready!"
```
