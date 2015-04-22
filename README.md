# TF2binds

This is a mapping of custom keybinds for Team Fortress 2. Includes class-specific binds.

### Applying to TF2 on Windows
Copy the CustomBinds directory into this directory:  
```
C:\Program Files (x86)\Steam\SteamApps\common\Team Fortress 2\tf\custom
```
Then launch TF2.  

### How it works
TF2 parses your `~\tf\custom` folder for custom content (sounds, models, scripts, etc). Each subfolder in the `custom` directory represents an individual mod. In effect, CustomBinds is a mod for TF2's `~\tf\config\config.cfg`.

The subdirectory in `~\custom\CustomBinds\` is called `scripts`. This tells TF2 which content folder under `~\tf\` will be modified. In `~\custom\CustomBinds\scripts\`, you will find all the `*.cfg` files that modify TF2's default keybind configuration.

`autoexec.cfg` should start out as a copy of the default `config.cfg` from `~\tf\config\`. From there, you can modify `autoexec.cfg` to your liking with all the binds you want to have. This will be a 'global' custom bind configuration that affects all classes.

### Custom binds for individual classes
You can also customize binds for individual classes to override individual 'default' bind behavior set by `autoexec.cfg`. In this situation, the possible class files are named as follows:

```
scout.cfg
soldier.cfg
pyro.cfg
demoman.cfg
heavyweapons.cfg
engineer.cfg
medic.cfg
sniper.cfg
spy.cfg
```

For example, if you just want a special bind for the Medic class which announces to the team that you have an Ubercharge ready that you want to assign to the G key, you would create a `.cfg` file in `~\custom\CustomBinds\scripts\` called `medic.cfg`. This config script will execute when you first select or switch to the Medic class. It is recommended, for reasons elaborated below, that you create the `.cfg` files for all classes pre-populated with at least one special command.

```
// medic.cfg
bind g "say_team Ubercharge ready!"
```

This is where it gets a little bit confusing. If you switch to a different class, G will still be bound to `"say_team Ubercharge ready!"`. It was been overridden by `medic.cfg`. Switching to any other class will not automatically override it back to its default bind from `autoexec.cfg`, unless the class you switch to has one of two things:

1. A line to bind G to a different action in the config file for that class
2. A line to restore the 'default' configuration from `autoexec.cfg` before applying class-specific binds
 
Option 1 will explicitly rebind G to the desired action. You may want this if G will perform a unique action for each class. However, it is not recommended that you explicitly rebind G if you just want to restore it to the 'default' value from `autoexec.cfg`. There is an easier way.

Option 2 requires the addition of only one line to the top of each class config file (example given for scout):

```
// scout.cfg
exec autoexec.cfg
bind j "say_team I got a bucket of chicken."
```

If you switch to scout from medic, G will no longer be bound to `"say_team Ubercharge ready!"` from `medic.cfg`. `exec autoexec.cfg` will restore all binds to their 'defaults' given in `autoexec.cfg`. Also, J will now be bound to `"say_team I got a bucket of chicken."`
