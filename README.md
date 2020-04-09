# os-1-msinstall
## Задание 1. Создание скрипта для автоматизации установки под Windows
---
### `auto_install_software.txt.bat`
\
__7-zip installer__
```shell
"7z1604-x64.msi" /passive /norestart /le "C:\Users\%username%\Desktop\opersis\7zip-log.txt" TARGETDIR="C:\Program Files\7-Zip"
```

__PaintNet installer__
```shell
"paintnet_4.2.10.exe" /auto TARGETDIR="C:\Program Files\Graphics\Paint" DESKTOPSHORTCUT=1
```

__Inkscape installer__
```shell
"inkscape-0.92.4-x64.msi" /qr /norestart /lw "C:\Users\%username%\Desktop\opersis\inkscape-log.txt" TARGETDIR="C:\Program Files\Graphics\Inkscape"
```

__LibreOffice install__
```shell
"LibreOffice_6.4.2_Win_x86.msi" /passive /norestart /le "C:\Users\%username%\Desktop\opersis\libreoffice-install-log.txt"
"LibreOffice_6.4.2_Win_x86_helppack_ru.msi" /quiet /forcerestart
```

__Notepad++ installer__
```shell
"npp.7.8.1.Installer.x64.exe" /S
```

---
### `jre_installer.bat`
```shell
mkdir C:\Java\JRE
echo INSTALL_SILENT=Enable> %cd%\jcfg42.txt
echo INSTALLDIR=C:\Java\JRE>> %cd%\jcfg42.txt
echo WEB_ANALYTICS=Disable>> %cd%\jcfg42.txt
echo WEB_JAVA=Enable>> %cd%\jcfg42.txt
"jre-8u241-windows-x64.exe" INSTALLCFG="%cd%\jcfg42.txt" /L %cd%\jre-log.log
del %cd%\jcfg42.txt
```
