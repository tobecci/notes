# My notes on vue.js

## how to use vue router

```javascript
// yarn add vue-router
// in the main.js file type below code
import VueRouter from 'vue-router'
import Routes from './routes.js';
Vue.use(VueRouter);
const router = new VueRouter({
  routes: Routes,
  mode: 'history',
//   default mode is "hash"
});
new Vue({
  render: h => h(App),
  router: router
}).$mount('#app')

// contents of the routes.js file are
import showBlogs from './components/showBlogs.vue';
import listBlogs from './components/listBlogs.vue';
export default [
    {path:'/',component:showBlogs},
    {path:'/list',component:listBlogs},
]
// we are exporting an array of objects
```

## using mixin in vue

``` javascript
// an example
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

```javascript
filters: {
    "to-uppercase": (value) => {
      return value.toUpperCase();
    },
  },
// usage
 <h3>{{ blog.title | to-uppercase }}</h3>
```
