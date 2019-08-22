# Vuetify notes

## vuetify props and their functions

* `height="300"` for changing the height of a component
* `max-width="300"` setting the maximum width of an element
* `right` and `left` floats items to the right and left of their containers respectively
* fab on buttons with icons inside makes the button rounded

## vuetify classes and their 

* class="mx-auto" for centering an element on a page, by setting the margins to auto

* class="hidden-md-and-up" for setting breakpoints, to hide on md(medium screens) and up. valid screen sizes are `xs` (xtra small, e.g mobile), `sm` (small e.g tablets) `md` (medium e.g laptop) `lg` (large e.g desktop) `xl` (xtra large e.g 4k and ultra wides)

* for setting visibility we use **hidden-(breakpoint)-(condition)**
`breakpoint - e.g xs, sm, md`
`condition - e.g and-up, and-down, only`

## vuetify navigation drawer
is added with 
```txt
<v-navigation-drawer app v-model="drawer" temporary>
  <p>test</p>
</v-navigation-drawer>
```

* temporary add an overlay on it, to remove it when other parts of the screen is clicked
* we add list items using `v-list` they are like `<ul>` tags in html, inside the `v-list` we have the list tiles i.e `v-list-tile` they are like `<li>` tags in html

we embed the list code like so
```
<v-list>
<v-list-tile>
  <v-list-tile-content>
    <v-list-tile-title>Dashboard</v-list-tile-title>
  </v-list-tile-content>
</v-list-tile>
</v-list>
```

## vuetify toolbar
```
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

## vuetify divider

* `v-divider` added a horizontal rule across the page section

## vuetify chips

* `v-chips` it takes normal props like `small`, 

> in order to use vuetify props on normal html elements we call them in classes e.g to use the `right` prop in a `div` we write `<div class="right">`