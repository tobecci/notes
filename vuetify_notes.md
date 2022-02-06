# Vuetify notes

## vuetify props and their functions

* `height="300"` for changing the height of a component
* `max-width="300"` setting the maximum width of an element
* `right` and `left` floats items to the right and left of their containers respectively
* fab on buttons with icons inside makes the button rounded

## vuetify classes and their functions

* class="mx-auto" for centering an element on a page, by setting the margins to auto

* class="hidden-md-and-up" for setting breakpoints, to hide on md(medium screens) and up. valid screen sizes are `xs` (xtra small, e.g mobile), `sm` (small e.g tablets) `md` (medium e.g laptop) `lg` (large e.g desktop) `xl` (xtra large e.g 4k and ultra wides)

* for setting visibility we use **hidden-(breakpoint)-(condition)**
`breakpoint - e.g xs, sm, md`
`condition - e.g and-up, and-down, only`

## vuetify navigation drawer

is added with

```js
<v-navigation-drawer app v-model="drawer" temporary>
  <p>test</p>
</v-navigation-drawer>
```
* without putting the `absolute prop it wont show up`
* temporary add an overlay on it, to remove it when other parts of the screen is clicked
* we add list items using `v-list` they are like `<ul>` tags in html, inside the `v-list` we have the list tiles i.e `v-list-tile` they are like `<li>` tags in html

we embed the list code like so

```js
<v-list>
<v-list-tile>
  <v-list-tile-content>
    <v-list-tile-title>Dashboard</v-list-tile-title>
  </v-list-tile-content>
</v-list-tile>
</v-list>
```

## vuetify toolbar

```js
  <v-toolbar app >
      <v-toolbar-side-icon color="grey--text" @click="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title class="text-uppercase grey--text">
        <span class="font-weight-light">Todo</span>
        <span class="font-weight-bold">Ninja</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
      color="grey"
      flat
      >
        <span>Sign Out</span>
        <v-icon right>exit_to_app</v-icon>
      </v-btn>
    </v-toolbar>
```

* `v-toolbar-side-icon` is used to add a harmburger icon for clicking
* `v-toolbar-title` for adding a toolbar title which is floated to the left

## adding router links to vuetify components

we do this by using a `route` prop and binding the link to the `to=""` prop

* example `<v-btn router :to=""></v-btn>`

## vuetify container

`v-container` is used to contain items to a central width, it also helps to stretch the content across various screen sizes

## vuetify grid system

* `v-layout` takes `row` or `column` props, to define a layout on a row or column, it can also take a `wrap` prop to wrap items
* we use `v-flex` inside the `v-layout` element to define items inside the layout, it takes breakpoint width props e.g `xs12` (occupy 12 cols of with on extra small screens ), or `md6` etc
* adding `block` prop to `v-btn` element makes it take up the full width of the flex
* if we are not taking up all the available space in a `v-layout` we can justify the contents inside it by using the following props `justify-space-around` `justify-space-between` `justify-center`

### for vuetify 2, it has changed 
we use `class="d-flex flex-row justify-end"` to make an element a flex box, row, and justify to end of the container

## vuetify divider

* `v-divider` added a horizontal rule across the page section

## vuetify chips

* `v-chips` it takes normal props like `small`

> in order to use vuetify props on normal html elements we call them in classes e.g to use the `right` prop in a `div` we write `<div class="right">`

## vuetify tooltips

are created with the `v-tooltip` tag, it takes either `top` or `bottom` prop, inside the tooltip element there should be an element with a `slot="activator"` prop on it, this element is what activates the tooltip, a `<span>` element below the activator element controls what is shown in the tooltip

## vuetify text formatting

* we use `class="text-xs-center"` to center text for xs screens and above

## vuetify image

* we generally put images inside `v-responsive` tags*

## Vuetify avatars

* its basically an image in the shape of a circle
* we use it by calling the `v-avatar` tag, it can also take a `size=""` prop to define how big or small it is

## vuetify expansion panel

create an expansion panel with `v-expansion-panel` we input `v-expansion-panel-content` inside it, and we create an element inside the panel-content with `slot="header"` prop

```js
<v-expansion-panel>
  <v-expansion-panel-content>
    <div slot="header">panel text</div>
    <v-card>
      <v-card-text>card text</v-card-text>
      <div>due by xx.xx.xx.xx</div>
    </v-card>
  </v-expansion-panel-content>
</v-expansion-panel>
```

for vuetify 2
create an expansion panel with `v-expansion-panels`, inside of it goes `v-expansion-panel`, and inside of that goes `v-expansion-panel-header` and `v-expansion-panel-content`


## vuetify menus

`v-menu` props `offset-y` or `offset-x` to make sure the items dont cover the button
we should generally use `v-list` and `v-list-item` and `v-list-item-title` inside it as well

## vuetify dialogs

`v-dialog` embedded inside is an element with `slot="activator"` prop, below the activator is the code that shows in the popup

## vuetify forms

`v-form` inside goes `v-text-field` or `v-textarea`, we add icons to text fields by using the `prepend-icon=""` prop

## vuetify date picker

we call this by using `v-date-picker`, we also used date-fns to format the date, `yarn add date-fns`, we call it into the component using `import format from 'date-fns/format';`
we use the format function we imported by calling `format(date, 'Do MMM YYY')`, the `'Do MMM YYY'` if just one of the formats used in formatting dates in the date-fns
when i use the `format` it does not work right.

## vuetify form validation

we bind `:rules=""` prop to an array, e.g `:rules="myRules"`, in the data we have

```js
data(){
  myRules: [
    v => v.length >= 3 || 'Minimum lenght is 3'
  ],
  // format is
  // (variable) => (condition) || (response when condition is false)
}
```

to make sure the button does not submit when there are errors we add some code to the function submitting the form

```js
submit(){
  if(this.$refs.ref_value.validate()){
    // fire your action here
  }
  // where v-form element has ref="ref_value"
}
```

## importing stuff in vuetify

* `@/` represents the src folder
* `/` represents the public folder

## firestore example in vuetify

* create a file in `src` folder called fb.js and place the following code inside

```js
import firebase from 'firebase/app';
import 'firebase/firestore';
var firebaseConfig = {
    apiKey: "AIzaSyAq3I9b4w4nYVV_B-uNDJUZCKNLy0S0Jf0",
    authDomain: "tobecci-todo-app.firebaseapp.com",
    databaseURL: "https://tobecci-todo-app.firebaseio.com",
    projectId: "tobecci-todo-app",
    storageBucket: "tobecci-todo-app.appspot.com",
    messagingSenderId: "584181190898",
    appId: "1:584181190898:web:db63a861eb15ee71"
};
//the firebaseConfig will be the one provided for your project
firebase.initializeApp(firebaseConfig);
const db = firebase.firestore();
db.settings({ timestampsInSnapshots: true });
export default db;
```

* in order to use it we use `import db from "@/db";`
* to add data we use `db.collection('projects').add(this.project).then(() => {//code to run});` where `'projects'` is the name of the collection you want to add to

## vuetify button loaders

we make a button show the loading icon by setting the `:loading=""` prop to true, this means when you start performing an action set it to true and when the action is completed, set it to false

## vuetify snackbars

this is a little thing that appears at the top
`v-snackbar` then inside goes `span` to add the message and under it is `v-btn` to close the snackbar, it can take a `:timeout="4000"` prop to set it to display for `4 secs`, it also takes a `top` or `bottom` prop to make it to show at the top or bottom

## defining custom colors in vuetify

```js
// in plugins/vuetify.js
Vue.use(Vuetify, {
  iconfont: 'md',
  theme: {
    primary: '#9652ff',
    success: '#3cd1c2',
    info: '#ffaa2c',
    error: '#f83e70'
  }
})
```

## emitting events from one component to another

`this.$emit('event_name');` to emit events, it can take parameters

## firetore realtime listeners

we connect to the firestore and get data using

```js
db.collection('collection_name').onSnapshot((res) => {
  const changes = res.docChanges(); 
  // changes can either be added, removed or modified
  // changes is an array
  changes.forEach(change => {
    if(change.type === "added" ){
      ...change.doc.data(), //gets and spreads the data in the document
      id: change.doc.id,
    }
  });
});
```

### vuetify 2 new toolbar

we now use `v-app-bar` to add toolbar in vuetify

## vuetify 2 activators

* the activator element should be inside a `template` element with `v-slot:activator="{on}"` prop, where on is the name given to the activator element, an example is given below
* `v-on="on"` is an example of the naming

## Hiding elements at certain breakpoints

* to hide elements on xs screens and up we use `.d-xs-none`
* to hide on xs only we use `.d-xs-none d-sm-flex`

