Vue Naming
==========

Vue is unopinionated about how to name files within the project. This can lead to calamity as different developers introduce varying conventions. This proposes a **resourceful** approach to component file naming.

### At a glance

- Component filenames are ProperCased and mixins are snake_cased.
- Components live entirely in `src/components/` and `src/views/`.
- Components are resourcefully named when possible: index, show, new, edit.
- Entry-point components live at the `src/views/{resource}/` level and not any deeper.
- Child components live at the `src/views/{resource}/` level or deeper.
- Prefix child components and partially reused components in `src/components` with an underscore `_`.

### Generic Components

**Globally reusable** components, relevant to any area of your app, live in `src/components`. Components that are generic to **one area** of the app and cannot be easily reused anywhere else also live in `src/components`, but are prefixed with an underscore as in `_Component.vue`.

### Resourceful route entry points

Components that are the **entry point to any route** live in a subdirectory of `src/views`. An entry point component means it's referenced as the `component` property of any route object in your `routes.js` file.

Entry point components never live more than one level deep in `src/views` (i.e. `src/views/Foos/Index.vue` is bad).

If the component is resourceful, name its file after the verb it represents (i.e. `Index.vue`, `Show.vue`, `New.vue`, `Edit.vue`), and the directory for the name of the resource. `src/views` has nothing but directories that are named for a resource or object when possible.

For example, given a route like:

```js
export default [
  {
    path: 'foo-bars',
    name: 'FooBars',
    component: FooBarIndex
  },
]
```

The component `FooBarIndex` would live in `src/views/FooBars/Index.vue`.

### Child components

Components that are imported by any entry point component live in `src/views/{resourceful name}/`. Use directories of that to further group children, when it makes sense.

Child component filenames start with a `_`, such as `_FormActions.vue`. This convention helps clarify a parent-child relationship between two or more components.

Mixins also live one level deep in a resourceful directory, for example `src/views/{resourceful name}/formatters.js`. Mixin filenames are snake cased.

Use descriptive words to make it obvious what your partial component is. For example, `Fieldset` for a piece of a form, or `FormControl` for a single more complex form control.
