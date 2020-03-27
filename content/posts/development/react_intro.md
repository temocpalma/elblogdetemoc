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

   * **className** instead of *class*
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
[Cerrar](/posts/development)
