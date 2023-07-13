<h1>
advanced-guide
</h1>

<p>this guide should help people how to use modules, autoexec, gameoverrides and pre-comfig.
</p>

<p>support <a href="https://github.com/mastercoms">mastercoms</a>
</p>

# modules

* modules are used to customize the settings in your preset that you can modify or change the way your preset behaves like **fps cap** that you can change your fps to cap your frame rate or unrestrict it. 

* you should read the [docs modules](https://docs.mastercomfig.com/en/latest/customization/modules/) and here you can see the list of modules that are available and their functionality. after you have found what you want to edit, open **modules.cfg** and remove `//` slashes and edit.

**before**

```````
//messages=on
// on, hide, off
```````

**after**

``````
messages=hide
// on, hide, off
``````

the on, hide, off is your choice whether you want it on, hide it, or just disable it.

# autoexec

* autoexec is a config file where scripts, binds or commands can be placed to run each time you start TF2.

what does an autoexec config look like?

here's an example of what an autoexec config look like (autoexec does not look all the same, it is based on your own preference).
https://github.com/uesu/uesu-tf2-cfg/blob/master/overrides/autoexec.cfg

where do i start to make my own autoexec config?

there is a template to help you make your own autoexec config.
https://github.com/mastercomfig/mastercomfig/releases/latest/download/autoexec_template.cfg

**note**: this affects all class.

# gameoverrides

* this unsets or unbinds itself, for example, if you are using a crouch jump script on soldier but you don't want to use the script on the other class you can use **game_overrides** to unbind the script.

* if the script or bind is for this class only (example = scout) you should put it on **scout.cfg** and use game_overrides to place the default tf2 key to it. if it is for all class, put the script on game_overrides (example = quick switch loadout).

https://wiki.teamfortress.com/wiki/List_of_default_keys

https://wiki.teamfortress.com/w/images/c/c8/Config_default.cfg.txt

**example 1**:

* crouch jump script on soldier:

```
alias +crouchjump "+duck; +jump"
alias -crouchjump "-jump; -duck"
bind "space" "+crouchjump"
```

just put:

```
bind space +jump
```

on game_overrides and it will not run when changing other class.

video example: https://youtu.be/DussnNwmgfo ; https://youtu.be/RbB29yptKVw

**note**: game_overrides will execute first before the class file, which means the **script** will always happen afterwards and every other class change will re-bind to **+jump**.

**example 2:**

* blocky-lightmaps w/ null-movement on scout:

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

simply put:
```
mat_filterlightmaps 1
bind w "+forward"
bind a "+moveleft"
bind s "+back"
bind d "+moveright"
```
now blocky-lightmaps w/ null-movement will not be executed when changing other class.

# pre-comfig

* pre_comfig can change your preset to high, medium or low without downloading a medium, high or low preset. you may need to use modules on **very low** to allow killfeed, messages and sheens.

preset names:
```
ultra
high
medium-high
medium
medium-low
low
very-low
```
example = `preset=very-low`

#

<h4 align="center">
tips
</h4>

* view file name extensions and hidden items


![intro](https://github.com/uesu/advanced-guide/blob/master/image.png)


* edit cfg

https://notepad-plus-plus.org/downloads/
