<style>
th, thead {
    border-top:1pt solid;
    border-bottom: 2px solid;
    border-left: none;
    border-right: none;
}
td {
    border-top: 1px solid;
    border-bottom: 1px solid;
    border-left: 1px solid;
    border-right: 1px solid;
}
</style>

# React: Building Custom Hooks

## <span style="color:lightgreen">What are "Custom Hooks"?:</span>

---

Custom hooks are, in the end, just regular functions (just as built-in hooks like useState are) but they are functions which can contain stateful logic. You can build custom hooks to outsource stateful logic into reusable functions

- Unlike regular functions (not component functions), custom hooks can use other React hooks, React state and other custom hooks

With custom hooks you can outsource logic, which you might be using in different components, into a custom hook which you can then call from all these various components

---

<br>

## <span style="color:lightgreen">Basic Rules:</span>

---

If you call a custom hook in one of your components and that component, for example,registers a state then this state and effect will be tied to the component in which you use the custom hook.

- If the custom hook is used in multiple components, then each component will receive its own state and will not be shared

Custom hooks have to start with 'use' so that react knows that its to be treated as a custom hook
