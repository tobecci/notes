
# Vuex Notes

## how to use vuex

in src/store/store.js
```js
import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);

export const store = new Vuex.Store({
  state: {
    products: [
        {name: "Banana skin", price: 20},
        {name: "Tiny star", price: 40},
        {name: "Green shells", price: 60},
        {name: "Red shells", price: 80},
      ]
  }
});

```
in main.js file

```js

import { store } from './store/store.js';
new Vue({
  render: h => h(App),
  router: router,
  // add below code
  store: store,
}).$mount('#app')
```


we access the store using computed properties, for example
```js
computed : {
  products: function(){
    return this.$store.state.products;
  }
}

```
---

## using getters in vuex

we define getters with 
```js
getters: {
    salesProducts: function(state){
      var salesProducts = state.products.map(function(product){
        return {
          name: "**" + product.name + "**",
          price: product.price / 2,
        };
      });
    return salesProducts; 
    },
  },
  ```
but we call it within a computed property like so

```js
salesProducts: function(){
  return this.$store.getters.salesProducts;
},
```

---

## How to use mutations in vuex

mutators are used for changing data in a vuex app and they can be tracked, they are created as so
```js
mutations: {
    reducePrice: function(state){
      state.products.forEach(function(product){
        product.price--;
      });
    },
  },
```
they are called by commiting, the above is called by using
```js
methods: {
  reducePrice: function(){
    this.$store.commit('reducePrice');
  },
},
```
> you should not edit vuex store data without mutators, also we should not do any asynchronous tasks inside them

get into the practice of not using mutations directly, instead call them from within an action

>passing a second parameter in this.$store.commit('reducePrice','secondParameter'); allows the reducePrice mutation to receive and use that data 
---

## How to use actions in vuex

actions can be used to perform asynchronous tasks in vuex, we use it like so
```js
actions: {
  reducePrice: function(context){
    setTimeout(function(){
      context.commit('reducePrice');
      //it takes the name of the mutation as an argument
    },2000);
  },
},
```
actions are called by using 
```js
this.$store.dispatch('actionName');
```
>the `context` is kinda like the store instance
>this.$store.dispatch('reducePrice','secondParameter'); allows the reducePrice action to receive and use that data 


