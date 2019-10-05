 # Props
 Props of component enable us to reuse a component. We commonly use props to render components with some particular values changed.

 Defining a component:
 ```javascript
    function Header(props) {
        <h1>Welcome, {props.name}</h1>
    }
 ```
 Or as a class:
 ```javascript
 class Header extends React.Component {
     render() {
         return(
             <h1>Welcome, {this.props.name}</h1>
         );
     }
 }
 ```
 This is how we will use such an element:
 ```javascript
    ReactDOM.render(<Header name="Hari"/>, getElementById('root'));
 ```
Or as nested components:
```javascript
    function App(){
        <Header name="Adith"/>
        <Header name="Abish"/>
    }
```

# States and Event Handling
```javascript
import React from 'react';
import logo from './logo.svg';
import './App.css';

class App extends React.Component {
  constructor(){
    super();
    this.state = {
      users: [],
      currentUser: null
    }
    this.addUser = this.addUser.bind(this);
    this.handleInput = this.handleInput.bind(this);
  }
  addUser() {
    let currentState = this.state.users;
    currentState.push(this.state.currentUser)
    this.setState({users: currentState})
  }
  handleInput(event){
    const target = event.target;
    const value = target.type === 'checkbox' ? target.checked : target.value;
    this.setState({
      currentUser: value
    });
  }
  render(){
    let list = [];
    for(let i=0; i<this.state.users.length;i++){
      list[i] = <div>{this.state.users[i]}<br /></div>
    }
    return(
    <div>
      <input
            name="userName"
            value={this.state.currentUser}
            onChange={this.handleInput} />
      <button onClick={this.addUser}>Add User</button>
      <div>
        {list}
      </div>
    </div>
    )
  }
}

export default App;
```

Instead of using the for loop, we can use `map` function like:
```javascript
    users = this.state.users;
    let list = users.map(user => <UserComponent name={user.name}>)
```
The above works for an array of objects as well.

### Reference Links
[Forms](https://reactjs.org/docs/forms.html)  
[State](https://reactjs.org/docs/state-and-lifecycle.html)  
[Events](https://reactjs.org/docs/handling-events.html)