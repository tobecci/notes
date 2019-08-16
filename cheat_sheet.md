# sphinx cheatsheet

## codeigniter font awesome problem solution

```
$root=(isset($_SERVER['HTTPS']) ? "https://" : "http://").$_SERVER['HTTP_HOST'];
$root.= str_replace(basename($_SERVER['SCRIPT_NAME']), '', $_SERVER['SCRIPT_NAME']);
$config['base_url'] = $root;
```

## Heroku

```
heroku login --interactive
heroku apps:create my-site
git push heroku master
```

## lxde ctrl not working, the workaround

```
A temporary workaround may be opening the ~/.config/openbox/lxde-rc.xml config file in a text editor, finding the section and then manually adding the "C-" to the field like this:
<keybind key='C-A-Up'>
<keybind key='C-F1'>
<keybind key='C-A-Tab'>
```

## index.php removal not working solution

```
open /etc/apache2/sites-available/000-default.conf and replace the <Directory > tag with the code below

<Directory "/var/www/html">

       Options Indexes FollowSymLinks MultiViews

       AllowOverride All

      Order allow,deny

      allow from all

      Require all granted

</Directory>
```

<!-- https://mygradr.web.app/RLSn4T6mJmQBORq7vnOt/!#intro -->

## money that chiboy gave to me 

```
- monday: 2500
- tuesday: 2500
- wednesday: 
- thursday:
- friday: 
```

## allowing copy and paste in gradr

```
var allowPaste = function(e){
      e.stopImmediatePropagation();
      return true;
}
document.addEventListener('paste',allowPaste,true);
```

## how to use vue router

```
yarn add vue-router
in the main.js file type below code
import VueRouter from 'vue-router'
import Routes from './routes.js';
Vue.use(VueRouter);
const router = new VueRouter({
  routes: Routes,
  mode: 'history',
});
new Vue({
  render: h => h(App),
  router: router
}).$mount('#app')

contents of the routes.js file are
import showBlogs from './components/showBlogs.vue';
import listBlogs from './components/listBlogs.vue';
export default [
    {path:'/',component:showBlogs},
    {path:'/list',component:listBlogs},
]
we are exporting an array of objects
```

## using mixin in vue

```
an example
import searchMixin from '../mixins/searchMixin.js';
mixins: [searchMixin],
inside searchMixin.js
export default {
    computed: {
        filteredBlogs: function(){
            return this.blogs.filter((blog) => {
              return blog.title.match(this.search);
            })
          },
    }
}
```

## using filters in vue

```
filters: {
    "to-uppercase": (value) => {
      return value.toUpperCase();
    },
  },
usage
 <h3>{{ blog.title | to-uppercase }}</h3>
```

## syscomptech mailchimp credentials

```

username: syscomptech_mailer
pass: Syscomptech`1234567890
```
