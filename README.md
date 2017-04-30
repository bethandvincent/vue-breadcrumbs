[![npm](https://img.shields.io/npm/dt/vue-breadcrumbs.svg)]()
[![npm](https://img.shields.io/npm/v/vue-breadcrumbs.svg)]()
[![GitHub stars](https://img.shields.io/github/stars/samturrell/vue-breadcrumbs.svg?style=social&label=Star)]()

# vue-breadcrumbs

Vue breadcrumbs builds on the official vue-router package to provide simple breadcrumbs. This package is backwards compatible to support both Vue 1.x and Vue 2.x. 

## Installation
```html
<script src="../dist/vue-breadcrumbs.min.js"></script>
```

```js
Vue.use(VueBreadcrumbs)
```

or via npm:

```sh
$ npm install vue-breadcrumbs
```

```js
import VueBreadcrumbs from 'vue-breadcrumbs'

Vue.use(VueBreadcrumbs)
```

Define the matching breadcrumb text in your routes.

## Usage
### Vue 1.x 

Use the `breadcrumb:` property of a route or subRoute, e.g.:

```js
router.map({
  '/': {
    component: Page,
    breadcrumb: 'Home Page',
    subRoutes: {
      '/foo': {
        component: Foo,
        breadcrumb: 'Foo Page'
      },
      '/bar': {
        component: Bar,
        breadcrumb: 'Bar Page'
      }
    }
  }
})
```
 
### Vue 2.x

Use the `meta.breadcrumb:` property of a route or child route, e.g.:

```js
new VueRouter({
  routes: [
    {
      path: '/', 
      component: Page,
      meta: {
        breadcrumb: 'Home Page',
      },
      children: [
        {
          path: '/foo', 
          component: Foo,
          meta: {
            breadcrumb: 'Foo Page'  
          }
        },
        {
          path: '/bar', 
          component: Bar,
          meta: {
            breadcrumb: 'Bar Page'
          }
        }
      ]
    }
  ]
})
```

You can then render the breadcrumbs using the included `<breadcrumbs>` component or using your own markup logic with the global `this.$breadcrumbs` property which will return an array of active matched routes.

# License

[MIT](http://opensource.org/licenses/MIT)
