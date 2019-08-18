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
open /etc/apache2/sites-available/000-default.conf and replace the <Directory > tag with the code below

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

## syscomptech mailchimp credentials

```txt
username: syscomptech_mailer
pass: Syscomptech`1234567890
```

## My Gradr Assessment link

[gradr](https://mygradr.web.app/RLSn4T6mJmQBORq7vnOt/!#intro)
