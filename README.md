# vidyo64
<par>Instruction and files to install VidyoDesktop </par>

<par> Unpaking the .deb </par>

```bash
dpkg-deb -x VidyoDesktopInstaller-ubuntu64-TAG_VD_3_6_3_017.deb vidyobuild
dpkg-deb --control VidyoDesktopInstaller-ubuntu64-TAG_VD_3_6_3_017.deb vidyobuild/DEBIAN
```

<par> modifying the depends </par>
```bash
cat vidyobuild/DEBIAN/control | sed '/Depends: libxss1,libaudio2,libasound2,libqt4-gui (>= 4.8.1), libqt4-network/c\Depends: libxss1,libaudio2,libasound2,libqt4-network'>> vidyobuild/DEBIAN/control
```
<par> Repaking </par>
```bash
dpkg-deb -b vidyobuild vidyodesktop-custom.deb
```
<par> Installing </par>
```bash
sudo dpkg -i vidyodesktop-custom.deb
```
