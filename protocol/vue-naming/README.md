Vue App Naming Protocol
=======================

Vue is unopinionated about how to name files within the project. This can lead to calamity as different developers introduce varying conventions.

Here is a list of conventions that we all should follow when introducing new components, mixins, or other files to any Vue repo.

### How generic is my component?

- Truly generic, **globally-reusable** components live in `src/components`.
- Components that are generic to **one area** of the app and cannot be easily reused anywhere else also live in `src/components`, but are prefixed with an underscore as in `_Component.vue`.
- Components that are the entry point to any route live in a subdirectory of `src/views`.
- Components that are imported by any entry point component also live in a subdirectory of `src/views`.
- Any other view-specific code, such as mixins, also live in a subdirectory of `src/views`.

### Views - `src/views`
- All components are to use ProperCase.
- All directories should be named after a resource or object, when possible.
- Components that are the entry point to any route should be one level deep in these resourcefully-named folders.
- Components that are the entry point to any route should prefer resourceful names -- `Index.vue`, `Show.vue`, `New.vue`, `Edit.vue`, when possible.
- Components imported by any entry point should 
