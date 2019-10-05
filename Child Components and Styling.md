# Parent and Child Components
We can use nested components, i.e, components inside components to make our code more organized. We can then separete these components intro different files and group them in folders.

Example app having a main parent component(`App`) and three child components(`Header`, `Content` and `Footer`) with each component in it's own file can be coded as:  
In `App.js`: 
```javascript
import React from 'react';
//import ReactDOM from 'react-dom';

import Header from './Header';
import Content from './Content';
import Footer from './Footer';

function App() {
    return(
        <Header />
        <Content />
        <Footer />
    );
}

export default App;
//or ReactDOM.render(<App />, elem) if doing directly
```
In `Header.js`:
```javascript
import React from 'react';

function Header() {
    return(
        <h1>Our Header</h1>
    );
}

export default Header;
```
In `Footer.js`:
```javascript
import React from 'react';

function Footer() {
    return(
        <h1>Our Footer</h1>
    );
}

export default Footer;
```
In `Content.js`:
```javascript
import React from 'react';

function Content(){
    return(
        <p>Some content</p>
    );
}

export default Content;
```

# Adding Styles to Components

## Inline Styles
```javascript
    function Header(){
        return(
        <h1 style={{backgroundColor: "blue"}}>Hello World!</h1>);
    }
```
or 
```javascript
    function Header(){
        const styles = {backgroudColor: "blue",
                    color: "red"};
        return(
        <h1 style={styles}>Hello World!</h1>);
    }
```
### Conditional Styling
```javascript
    function Header() {
        let red = true;
        styles = {};
        if(red){
            styles.color = "red";
        }return(
        <h1 style={styles}>Hello World!</h1>);
    }
```
## Using stylesheets
```javascript
import './App.css';
function App(){
    return(
        <h1 className="heading"></h1>
    );
}
```
