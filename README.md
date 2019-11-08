# TastyWorks-snap
This is UNOFFICIAL snap for [TastyWorks trading platform](https://www.tastyworks.com/technology.html).  
Latest version of TastyWorks doesn't work on Ubuntu 16.04 LTS .  
This snap brings compatibility with all versions of Ubuntu.

# Build yourself
```bash
sudo snap install snapcraft --classic
git clone https://github.com/CoolSpot/tastyworks-snap
cd tastyworks-snap
snapcraft
snap install tastyworks-unofficial*.snap --dangerous
```
"dangerous" flag is necessary above because self-built snap is unsigned.

# Install from snap store
```bash
sudo snap install tastyworks-unofficial
```

# Known Issues
1. AppArmor logs show denied access to "/var/lib/snapd/desktop/icons/".  
   This is known issue of snap itself. See [forum](https://forum.snapcraft.io/t/reading-var-lib-snapd-desktop-applications-icons/13650).
2. Sound doesn't work. It is known issue of JavaFX under snap. See [forum](https://forum.snapcraft.io/t/sound-in-the-javafx-toolkit-is-broken/4606).

