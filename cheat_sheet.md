# sphinx cheatsheet

## codeigniter font awesome problem solution

```php
$root=(isset($_SERVER['HTTPS']) ? "https://" : "http://").$_SERVER['HTTP_HOST'];
$root.= str_replace(basename($_SERVER['SCRIPT_NAME']), '', $_SERVER['SCRIPT_NAME']);
$config['base_url'] = $root;
```

## Heroku

```txt
heroku login --interactive
heroku apps:create my-site
git push heroku master
```

## lxde ctrl not working, the workaround

```txt
A temporary workaround may be opening the ~/.config/openbox/lxde-rc.xml config file in a text editor, finding the section and then manually adding the "C-" to the field like this:
<keybind key='C-A-Up'>
<keybind key='C-F1'>
<keybind key='C-A-Tab'>
```

## index.php removal not working solution

```txt
open /etc/apache2/sites-available/000-default.conf and replace the <Directory > tag with the code below. in some cases you add it

<Directory "/var/www/html">

       Options Indexes FollowSymLinks MultiViews

       AllowOverride All

      Order allow,deny

      allow from all

      Require all granted

</Directory>
```

## allowing copy and paste in gradr

```javascript
var allowPaste = function(e){
      e.stopImmediatePropagation();
      return true;
}
document.addEventListener('paste',allowPaste,true);
```

## My Gradr Assessment link

[gradr](https://mygradr.web.app/RLSn4T6mJmQBORq7vnOt/!#intro)


## for apache file permission issues run

`sudo chmod -R 775 /var/www`

## fix wordpress ftp issue

* add `define( 'FS_METHOD', 'direct' );` to the wp-config file

## fix wordpress or server not writing to files

* run `chown www-data:www-data  -R wordpress` in terminal

## fix wordpress cant crop image problem

* run `sudo apt install php-gd` in terminal, and restart your apache server or system

## wine 32bit prefix
`WINEARCH=win32 WINEPREFIX=/home/tobecci/.wine winecfg`

## download free images
[pixabay](https://pixabay.com)

## how to find overflowing elements on a page

```js
var docWidth = document.documentElement.offsetWidth;

[].forEach.call(
  document.querySelectorAll('*'),
  function(el) {
    if (el.offsetWidth > docWidth) {
      console.log(el);
    }
  }
);
```
## aireplay kick algorithm
* `sudo airmon-ng start wlp12s0`
* `sudo airodump-ng wlp12s0mon`
* use `sudo iwconfig wlp12s0mon channel 1` to make sure `wlp12s0mon` is on channel `1`, that is the same channel as the AP
* `sudo aireplay-ng --deauth 0 -a E0:67:B3:1D:D5:0F wlp12s0mon`

## hng6 links
https://github.com/hngi/Team-NEMESIS/pull/22

## how to undo a commit

* `git reflog` to show the list of commits
* `git reset --hard [hash]` where `[hash]` is the hash of the commit e.g 75fecb3

## fix buffer overrun wine

NVIDIA FIX

Wine: Open a terminal and type: __GL_ExtensionStringVersion=17700 wine yourgame.exe (replace "yourgame.exe" with either jasp.exe or jamp.exe)

PlayOnLinux: Select the virtual drive, click on "configure" -> "miscellaneous" (tab) and type in the following "exec command" in the field below: export __GL_ExtensionStringVersion=17700

Launch thegame afterwards.

INTEL FIX

Wine: Open a terminal and type: MESA_EXTENSION_MAX_YEAR=2003 wine yourgame.exe (replace "yourgame.exe" with either jasp.exe or jamp.exe)

PlayOnLinux: Select the virtual drive, click on "configure" -> "miscellaneous" (tab) and type in the following "exec command" in the field below: export MESA_EXTENSION_MAX_YEAR=2003


##  adb tricks
list installed apps
pm list packages

uninstall a package
pm uninstall -k --user 0 package-name  

## auto mount modem in linux

`udevadm monitor --kernel --property --subsystem-match=usb` this code will print some output when a usb device is plugged or unplugged

create `/etc/udev/rules.d/5-usbstick-font.rules` and add 

```sh
ACTION=="add", SUBSYSTEM=="usb", ENV{PRODUCT}=="90c/1000/1100", RUN=="/bin/su username --command='path-to.sh'"
ACTION=="remove", SUBSYSTEM=="usb", ENV{PRODUCT}=="90c/1000/1100", RUN+="/bin/su username --command='path-to.sh'"
```

where `90c/1000/1100` is the product id

