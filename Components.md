# Components
## Introduction
Components are the basic building blocks of React. They are the visual elements that our users will see. React helps us create reusable components for our application very easily.

The code for a typical component in React looks like(If we're using the JSX syntax):
```javascript
class StudentList extends React.Component {
  render() {
    return (
      <div className="student-list">
        <h1>List of students attending the workshop</h1>
        <ul>
          <li>Adith</li>
          <li>Abish</li>
        </ul>
      </div>
    );
  }
}
```
Notice that the HTML like syntax inside the `return()` is not actually normal HTML but instead JSX. JSX is converted to a react element by React. We use JSX because it is simpler. If we didn't use JSX, the about return statement would look something like:
```javascript
React.createElement("div", {
  className: "studet-list"
}, React.createElement("h1", null, "List of students attending the workshop"), React.createElement("ul", null, React.createElement("li", null, "Adith"), React.createElement("li", null, "Abish")));
```
We refer to component properties the JavaScript way instead of the conventional HTML way. That's why we used `className=` instead of `class=` in the above JSX. A full list of such properties in JavaScript is [available here](https://developer.mozilla.org/en-US/docs/Web/API/Element).

To use a component declared like that, we use something like:
```javascript
<StudentList />
```

## Creating a Component and Showing it to User

In `App.js`:
```javascript
import React from 'react';

function App() {
  return (
    <h1>Hello World!</h1>
  );
}

export default App;
```
In `index.js`:
```javascript
import ReactDOM from 'react-dom';
import App from './App'

ReactDOM.render(<App />, document.getElementById('root'));
```
We can also do everything in one file as well. Like:
```javascript
import React from 'react';
import ReactDOM from 'react-dom';

function MyApp() {
    return (
        <h1>Hello World!</h1>
    );
}

ReactDOM.render(<MyApp />, document.getElementById('root'));
```

### Reference Links
[JSX Introduction](https://reactjs.org/docs/introducing-jsx.html)  
[React Components](https://reactjs.org/docs/components-and-props.html)