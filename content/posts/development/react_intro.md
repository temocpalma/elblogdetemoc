+++
title = "Introducción a React JS"
type="slide"
pre ="<i class='fa fa-anchor'></i> "
weight = 3
date = "2020-01-22"

theme = "sky"
[revealOptions]
transition= 'concave'
controls= true
progress= true
history= true
center= true
+++

### React JS

* Library JS: 

    <small>SPA's</small>

	 <small> Created by Facebook</small>

* Components:
   
    <small>encapsulate, re-use</small>

	 <small>presentation: JSX, css</small>

	 <small>logic: ECS6, state managment </small>

___

### Making a react app

* Pre-requisites: node

* Install create-react-app:
```
npm install -g create-react-app     
```

* Create the app:
```
create-react-app blog-app
```
   <small>*You must replace "blog-app" by your own app name*</small>

___

### Making first app (part 2)

* Start the app: 

   <small>Change into folder "blog-app" and execute next command</small>
```
npm start
```

   <small>To stop the app just press *Ctrl + C*</small>

___

### Application Structure

<img src="/img/react/app_structure.png" width="650" height="450" title="App Structure" />
___

### Application Structure (part 2)

* **node_modules:** project dependencies

* **public:** main html file

* **src:** components, css, index.js

* **package.json:** project dependencies declaration
___

### JSX = JavaScript XML

* Syntax to build the component markup

* It is transformed into javascript

* It can to be assigned into variables, or return in functions
```
const elem = <p>Paragraph text</p>;
```
   * Must be a single element:
   ```
   const elem = (
      <div>
         <span>Field:</span>
         <input type="text" />
      </div>
   );
   ```
___

### JSX (part 2) 

* It's like HTML with this differences:

   * **camelCase** naming instead of HTML attribute names
      * **className** instead of *class*, **tabIndex** instead of *tabindex*
      ``` 
      <div className="primary"> 
      ```

   * must close tags explicity
   ```
   <input type="text"></input>
   <img src="..." />
   ```
___

### JSX (part 3) 

* You can use js code along with JSX:
``` 
render() {
   const style = 'info';
   const title = 'React JS';

   return (
      <div className={style}>
         {title}
      </div>
   ); 
}
```
___

### JSX (part 4) 

* Ternary operator instead of *if...else*:
``` 
<div>
   {condition ? <h1></h1> : null}
</div>
```

* Display arrays:
```
render() {
   const fruits = ["orange", "apple", "banana"];
   return (
      <ul>
         {fruits.map(fruit =>
            <li>{fruit}</li>
         )}
      </ul>
   );
}
```
___

### Components

* UI piece: separate, reusable, isolated
* Declaration:
   * Like a function:
   ``` 
   const FunctionComponent = () => {
      return <h1>Function Component</h1>;
   }
   ```

   * Like a class (must contains **render** method):
   ```
   class ClassComponent extends Component {
      render() {
         return <h1>Class Component</h1>;
      }
   }
   ```
___

### Components (part 2)

* Create a component:
   * Create a file with same component name. For instance, write this code in a file with name *Title*, because component name is *Title*:
   ``` 
   import React, { Component } from "react";

   class Title extends Component {
      render() {
         return <h1>Title Component</h1>;
      }
   }

   export default Title;
   ```
   <small>Note: **You must export the component**</small>
___

### Components (part 3)

* Use a component:
   * For use the component created previously and supossing that its file is in same directory where is App component (*src* directory):
   ``` 
   import React, { Component } from "react";
   import Title from "./Title";

   class App extends Component {
      render() {
         return (
            <Title />
         );
      }
   }
   ```
___

### Components (part 4)

* Communication between components
   * they be pass into the component with attributes:
   ```
   class App extends Component {

      const userName = "Temoc";

      render() {
         return (
            <Title userName={userName}/>
         );
      }
   }
   ```
___

### Components (part 5)

* Communication between components (continuation)
   * <span style="color: tomato">**props**</span> object receive attributes values
   * when is a class component:
   ```
   class Title extends Component {
      constructor(props) {
         super(props);
      }

      render() {
         return (
            <div>
               <h1>Title Component</h1>
               <h2>{this.props.userName}</h2>
            </div>
         );
      }
   }
   ```
___

### Components (part 6)

* Communication between components (continuation)
   * when is a function component:
   ```
   const Title = (props) => {
      return <h1>Title Component ({props.userName})</h1>;
   }
   ```
___

### Component State

* Object that stores component information

* Only with class components

* When it is updated, the component is re-rendered

* It is local, encapsulated

___

### Component State (part 2)

* It is initialized in constructor
```
class Example extends Component {
   constructor(props) {
      super(props);

      this.state = {
         key1: "value1",
         key2: 100,
         key3: ["a", "b", "c"]
      }
   }
}
```
___

### Component State (part 3)

* It is updated with **setState** method

```
updateState() {
   const new_count = this.state.counter + 1;
   this.setState({
      counter: new_count
   });
}
```
___

### What else...

* Component lifecycle methods
* Http requests: Axios
* Testing: Jest, Enzyme
* Global state: Redux
* Error handler: ErrorBoundary

___


[Cerrar](/posts/development)
