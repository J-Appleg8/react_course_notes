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

# React: Behind The Scenes

## <span style="color:lightgreen">React & ReactDOM:</span>

---

React itself does not know the web or the browser, React knows how to work with components but it doesnt care whether those components contain HTML elements or fictional elements.
ReactDOM cares about that in the end in order to bring real HTML elements to the screen.

| React                                          | ReactDOM                                     |
| ---------------------------------------------- | -------------------------------------------- |
| Js library for building user interfaces        | Interface to the web                         |
| Works components, states, and component states | Real DOM - what the user sees                |
| props: data from the parent component          | React lets ReactDOM know if a change is made |
| context: component-wide data                   |                                              |

### <span style="color:turquoise">Virtual DOM:</span>

React is concerned about components, uses a concept called the virtual DOM. It determines how the component tree currently looks like, and what it should look like (for example: after a state update)

- That information is then handed off to ReactDOM which now knows about the differences, and how it should manipulate the real DOM to match that virtual DOM

| Components                                        | Real DOM                                                              |
| ------------------------------------------------- | --------------------------------------------------------------------- |
| Re-evaluated when props, state or context changes | Changes to real DOM are only made for differences between evaluations |
| React executes component functions                |                                                                       |

|

---

<br>

## <span style="color:lightgreen">useCallback():</span>

---

useCallback is a hook that allows us to store a function across component execution. So it allows us to tell React that we want to save a function, and that function should not be re-created with every execution

---

<br>

## <span style="color:lightgreen">First Summary:</span>

---

Components have one job in the end, the return the JSX code at the end of the function. In your React Components, you can work with state, or props or with context in order to make changes to the data that affect the component.

Whenever you change state in a component, that component (where the state changed) is re-evaluated and the component function is executed again. When the function is executed again it creates a 'new' output, which could be exactly the same as the previous output or it could be slightly different

- React evaluates all affected components and their output and compares the new output with the previous output to see if there are any changes
- Hands off any/all changes to ReactDOM, which ReactDOM will then take those changes and apply them to the real DOM in the browser
