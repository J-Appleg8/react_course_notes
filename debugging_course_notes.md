ReactJs

You build a Component Tree

- The top component is rendered directly into the HTML page
- All the other components will not be registered but will be used as regular HTML elements

A component in React is just a JavaScript function

---

<br>
props.children:

- the value of props.children will always be the content between the opening and closing tags of your custom component

props.className takes any classes that are set to a custom component and uses it

```javascript
function Card(props) {
  const classes = 'card ' + props.className;
  return <div className={classes}>{props.children}</div>;
}

function ExpenseItem(props) {
  return (
    <Card className="expense-item">
      <ExpenseDate date={props.date} />

      <div className="expense-item__description">
        <h2>{props.title}</h2>
        <div className="expense-item__price">${props.amount}</div>
      </div>
    </Card>
  );
}
```
