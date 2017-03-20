# Vuex

- inspired by Flux, Redux and The Elm Architecture. Unlike the other patterns, Vuex is also a library implementation tailored specifically for Vue.js
- one-way data flow (unidirectional)
- passing props can be tedious for deeply nested components, and simply doesn't work for sibling components
- **solution**: extract the shared state out of the components, and manage it in a global singleton
- **catch**: Although Vuex helps us deal with shared state management, it also comes with the cost of more concepts and boilerplate. It's a trade-off between short term and long term productivity.
- if your app is simple, you will most likely be fine without Vuex. A simple global event bus may be all you need

> "Flux libraries are like glasses: you’ll know when you need them" – Dan Abramov, author of Redux.

- Vuex stores are reactive
- trigger a state change with the `store.commit` method
- mutation handler functions must be synchronous
- use the mapMutations helper which maps component methods to store.commit calls (requires root store injection). see: https://vuex.vuejs.org/en/mutations.html
- 
