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
