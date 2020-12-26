Prerequisites
•	Node (nodejs.org)
•	Knowledge on
o	HTML5
o	CSS3
o	JavaScript (ES6)
Installation:
node -v
npm -v
npm install create-react-app -g
create-react-app <project_name>
npx create-react-app <project_name>

Components in React
•	Class components
•	For representing a class component we have to use class keyword
•	render() for returning a statement
•	We have to aquire the properties from base class for implementing.
•	Functional components
•	We have to use function | ()=> for implementing a functional component
•	Can return a statement directly
•	High performance than class Component
Styling components
  // Inline styles
  <h2 style={{backgroundColor:"green"}}> Sample content </h2>`
  
  // Stying component using JavaScript object
  var style={
     backgroundColor: "reg",
     color: "#000"
   }


Composition
The process of combining multiple components together
React fragment
We have to use react fragments for avoiding number of divisions.
   <React.Fragment>
    <Header />
    <h2> Sample heading </h2>
   </React.Fragment>
   
   or
   
   <> 
      <Header />
      <h2> Hellow world </h2> <h2> Hi everyone</h2> 
      <App />
    </>


State in React
The concept of State provides a way to store the data in a component
  constructor(){
    super();
    this.state={
      "name":"Hanuman",
      "role":"Full stack developer"
    }
  }




Manipulating data from a state
 changeStateValues=()=>{
    this.setState({
      "name":"Rajesh",
      "role":"MERN developer"
    })
  }
  render(){
    return(
    <> 
      <Header />
    <h2 onMouseOver={this.changeStateValues}> {this.state.name} working as a {this.state.role} </h2> 
      <App />
    </>
    )}


  
Using prevState for manipulating the data of a state:-
  incrementCounter=()=>{
    this.setState(prevState=>(
      {counter: prevState.counter+1}
    ))
  }


Decrementing the value of the state:-
 decrementCounter=()=>{
    if(this.state.counter>0){
    this.setState(prevState=>(
      {counter: prevState.counter-1}
    ))
    }
  }


Using hooks concept for implementing state functionality in functional component
 import React,{useState} from 'react';
// import Header from './Header'


function App(){

  var initialData=()=>{
    setData({
      name:"Hanuman",
      role:"Full stack developer"
    })
  }

  const [data,setData]=useState({"name":"Hanuman","role":"Full stack developer"})
  return(
    <>
      <h2 onMouseOver={()=>{setData({name:"Rajesh",role:"MERN developer"})}} onMouseOut={initialData}> {data.name} is working as a {data.role} </h2>
    </>
  )
}

export default App;



HOOKS CONCEPT :-
import React,{useState} from 'react';

function App() {
  const [data,setData]=useState({"name":"Hanuman","role":"Full stack developer"})
  return ( 
    <>
    <h2> {data.name} is working as a {data.role} </h2>
    </>
  )
}
export default App;



Manipulate data :-

import React,{useState} from 'react';

function App() {
  const [data,setData]=useState({"name":"Hanuman","role":"Full stack developer"})
  return ( 
    <>
    <h2 onMouseOver={()=>{setData({"name":"Rajesh","role":"MERN Developer"})}}> {data.name} is working as a {data.role} </h2>
    </>
  )
}
export default App;


APPLYING DYNAMIC STYLES:-
 import React,{useState} from 'react';
// import Header from './Header'
import './App.css';

function App(){
  var style={
    background:"green"
  }

  var changeBackground=(e)=>{
    e.target.setAttribute('class','changeBackground')
  }

  const [data,setData]=useState({"name":"Hanuman","role":"Full stack developer"})
  return (
    <>
      <h2 onMouseOver={(e)=>{changeBackground(e)}}> {data.name} is working as {data.role}.</h2>
    </>
  )
}

export default App;

DATA MANIPULATE:-
import React,{useState} from 'react';

function App() {
  var changeData=()=>{
    setData({
      name:"Rajesh",
      role:"MERN developer"
    })
  }
 const [data,setData]=useState({"name":"Hanuman","role":"Full stack developer"})
  return ( 
    <>
    <h2 onMouseOver={changeData}>{data.name} => {data.role}</h2>
    </>
  )
}
export default App;

App.js                                   
import logo from './logo.svg';
import './App.css';
import Header from './Header'

function App(){
  
  return(
    <>
    <h2> MY NAME RAJA </h2>
    <Header name="raja" role="FRESHER" />
    </>
  )
}
export default App;

Header.js

	let Header=(props)=>{
    return(
        <header>
        <h2> {props.name} working as a {props.role}</h2> 
        </header>
    )
}
export default Header;


