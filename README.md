<h1>
advanced-guide
</h1>

<p>this guide should help people how to use modules, autoexec and gameoverrides.
</p>

<p>support <a href="https://github.com/mastercoms">mastercoms</a>
</p>

# modules

- modules are used for setting quality levels in presets, 
    - and can also be used in the `tf/cfg/user/modules.cfg` file to easily 
        - customize your config without searching for individual console variable values

* first, go to https://docs.mastercomfig.com/en/latest/customization/modules/ and find the list of modules that you want to put in the `modules.cfg`

* navigate to `tf/cfg/user/modules.cfg`

* once you've found what you want to add, just copy the `highlighted module command` and paste it to `modules.cfg`
    
**example:**

```
messages=enable // enables all text messages
killfeed=on // enables killfeed
killstreaks=off // disable killstreak banner
```

* `note`: update the modules if it is renamed!

# autoexec

- autoexec is a config file where scripts,
    - binds and commands can be placed to run each time you start `TF2`
      - simply put what `scripts, binds, and commands` you want to use on `autoexec.cfg`

`example cfg`:
https://github.com/uesu/cfg/blob/master/user/autoexec.cfg

`template`:
https://github.com/mastercomfig/mastercomfig/releases/latest/download/template.cfg

* `note`: this affects all class, take a look at my `config` and it might give you some ideas on what to put into your `autoexec.cfg`. if you would like to have more customizations to be placed on your `autoexec.cfg`, download the `template`

# gameoverrides

- `unsets / unbinds itself`
  - example if you are using `crouch jump script` on `soldier.cfg`
    - but don't want to use the script on `other class` you can use `gameoverrides.cfg` to unbind the script

* `note`: if the `script or bind` is for this `class only`, example = `scout`, you should put it on `scout.cfg` and then reset the `key` by putting the `default tf2 key` to `gameoverrides.cfg`. if it is for `all classes`, put the script on `gameoverrides.cfg` example = `quick switch loadout`

https://wiki.teamfortress.com/wiki/List_of_default_keys

https://wiki.teamfortress.com/w/images/c/c8/Config_default.cfg.txt

**example:**

* `crouch jump script` on `soldier.cfg`:

```
alias +crouchjump "+duck; +jump"
alias -crouchjump "-jump; -duck"
bind "space" "+crouchjump"
```

* just put:

```
bind space +jump
```

on the `gameoverrides.cfg` and it will not run when changing other class

`video example:` https://youtu.be/DussnNwmgfo

* `game_overrides.cfg` will execute first before the class file, which means the `script` will always happen afterwards and every other class change will re-bind to `+jump`

**more example:**

* `blocky-textures w/ null-movement` on `scout.cfg`

```
mat_filterlightmaps 1
bind w "+mfwd;mat_filterlightmaps 0"
bind a "+mleft;mat_filterlightmaps 0"
bind s "+mback;mat_filterlightmaps 0"
bind d "+mright;mat_filterlightmaps 0"
alias +mfwd "-back;+forward;alias cfwd +forward"
alias +mback "-forward;+back;alias cback +back"
alias +mleft "-moveright;+moveleft;alias cleft +moveleft"
alias +mright "-moveleft;+moveright;alias cright +moveright"
alias -mfwd "-forward;cback;alias cfwd"
alias -mback "-back;cfwd;alias cback"
alias -mleft "-moveleft;cright;alias cleft"
alias -mright "-moveright;cleft;alias cright"
alias cfwd
alias cback
alias cleft
alias cright
```

* simply put:
```
mat_filterlightmaps 1
bind "w" "+forward" //default "+forward"
bind "a" "+moveleft" //default "+moveleft"
bind "s" "+back" //default "+back"
bind "d" "+moveright" //default "+moveright"
```
* now `blocky-textures w/ null-movement` will not be executed when changing other class

#

<h4 align="center">
tips
</h4>

* `view file name extensions and hidden items`


![intro](https://github.com/uesu/advanced-guide/blob/master/image.png)


* `edit cfg`

https://notepad-plus-plus.org/downloads/
