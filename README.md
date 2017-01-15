{2017-01-15 SUN 13:25} Cloned from https://github.com/computerlyrik/dymoprint


dymoprint
=========

Linux Software to print with LabelManager PnP from Dymo


cloned for development from http://sbronner.com/dymoprint/

Changes:

- *some..*


### For ubuntu based distributions:
(should also work for debian, but not tested yet)
use **udev** and **modeswitch** configurations to work with the LabelManager PNP.
**modeswitch** changes the mode (and USB Id) from mass storage device to printer device.

    sudo cp 91-dymo-labelmanager-pnp.rules /etc/udev/rules.d/
    sudo cp dymo-labelmanager-pnp.conf /etc/usb_modeswitch.d/

and restart services with:

    sudo reload udev

([more info](http://www.draisberghof.de/usb_modeswitch/bb/viewtopic.php?t=947))


### Font management

Fonts are managed via **dymoprint.ini**

You may choose any TTF Font you like

You may edit the file to point to your favorite font.

For my Arch-Linux System, fonts are located at e.g.

	/usr/share/fonts/TTF/DejaVuSerif.ttf

It is also possible to Download a font from
http://font.ubuntu.com/ and use it.

### Additional libraries used:
*(todo..)*
- PIL/PILLOW
- [pyqrcode](https://github.com/mnooner256/pyqrcode) (used v1.0)

### ToDo
- (?)support multiple ProductIDs (1001, 1002) -> use usb-modeswitch?
- put everything in classes that would need to be used by a GUI
- ~~for more options use command line parser framework~~
- ~~allow selection of font with command line options~~
- allow font size specification with command line option (points, pixels?)
- ~~provide an option to show a preview of what the label will look like~~
- ~~read and write a .dymoprint file containing user preferences~~
- print graphics and barcodes
- ~~plot frame around label~~
- vertical print
