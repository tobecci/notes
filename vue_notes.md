# My notes on vue.js

## How to use vue router

```js
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

// to link to the components we use
<router-link to="/">Show Blogs</router-link>

// getting parameters from the url
data(){
  return {
    id: this.$route.params.id    
  }
}
// route is added with
{path: '/blog/:id', component: singleBlog},
```

## Using mixin in vue

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

## Using filters in vue

```javascript
filters: {
    "to-uppercase": (value) => {
      return value.toUpperCase();
    },
  },
// usage
 <h3>{{ blog.title | to-uppercase }}</h3>
```

## Creating directives in vue

```javascript
directives : {
  'rainbow': {
    bind(el, binding, vnode){
      el.style.color = "#" + Math.random().toString(16).slice(2,8);
    }
  }
},
```

## plugins i installed

* vue-router
* vue-resource
* storybook
* vuex
* axios
* material-icons
* font awesome 4
* font awesome 5

## Binding checkboxes in vue

```txt
we do this by binding all of the input boxes to one array variable
```

# passing props in vue

after binding data to an attribute we go to the js of the receiving component and  write

```js
props["prop-name"],
```
