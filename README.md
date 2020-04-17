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
3. If the snap doesn't work and running it from terminal gives you a long Java Exception trace ending with 
    ```
    Caused by: java.lang.NullPointerException
    at TastyJavaFx//com.sun.javafx.font.LogicalFont.<init>(LogicalFont.java:181)
    ```
    That is likely caused by a [corrupted font cache](https://forum.manjaro.org/t/spotify-suddenly-not-working/125237/14).
    To rebuild the font cache do the following in the terminal:
    ```
    sudo rm /var/cache/fontconfig/*
    rm ~/.cache/fontconfig/*
    fc-cache -r
    ```
