1. What is a JS expression?

2. What is a constructor? How does it initialize the state? 
In JavaScript classes, you need to explicitly call super(); when defining the constructor of a subclass.

3. What does setState do? 

Whenever `this.setState` is called, an update to the component is scheduled, causing React to merge in the passed state update and rerender the component along with its descendants. 
* When the component rerenders, `this.state.value` will be X, so you will see X in the grid. If you click on any square, X will show up. 

* React components can have state by setting this.state on the constructure, which should be considered private to the component. 
* First add a constructor to the class to initialize the state
* In JavaScript classes, you need to explicitly cak super(); when defining the constructor of a subclass 
* Replace the () => alert() event handler with () => this.setState({value : 'X'})

4. React dev tools, allows you to inspect the props and state of any of the components in the tree. 



Lifting State Up 

1. We want have state in one place, and alternate X and O

* To check if someone has one, we need to have all 9 squares in one place, rather than split these up across the Square components. 
* The best solution here is to store this state in the Board componenet, instead of each Square, and the Board componenet can tell each Square what to display/ 
* Store the state in the board component, instead of each Square. 


Important:
  * Whenever you want to aggregate data from two child componenets, or have child components communicate with one another, move the state upward so that it lives in the parent component. 
  * The parent can then pass state back to the children, via pops


2. We need to change wha happens when a square is clicked. 
   The usual pattern here is pass down a function from board to square that gets called when the square is clicked. 
   We are now passing down two props from board to square: value, and onClick 


Recap:
* the `onClick` on the Square button tells react to set up an event listener
* when the buttoned, React will call the onClick event in Square's render method 
* the event handler called `this.props.onClick` 
* board passed onClick={() => this.handleClick(i)} to Square, so when called, it runs `this.handleClick(i)` on the board
* we have not defined the handleClick() method yet on the Board

in sum:
  * we set up the event listener on the button
  * when we press the button, the handler will handler it
  * the value of handle is `this.props.onClick, this comes from Board
  * this will call handleClick(i) on the board

it is conventional in react use use `on` for names of attributes and `handle` for handler mehtods. 

3. .slice
* We call .slice() to copy the squares array instead of mutating the existing array. 
* We should be able to click on the squares and fille them. But states is stored in the Board componenet instead of each Square, let's continue building the game. 
* Controlled componenets, Square no longer keeps its own state, it received its value from the parent Board and informs its parent when clicked. 
* We call components like this controlled components 


4. Mutability vs. Immutability 

here are generally two ways for changing data. The first is to mutate the data by directly changing the values of a variable. 

mutable:
var player = {score: 1, name: 'Jeff'};
player.score = 2; 

immutable:
var player = {score: 1, name: 'Jeff'}
var newPlayer = Object.assign({}, player, {score: 2});

we're basically cloning an object, and assigning score in the immutable version. 

5. Determining when to rerender in React: 

* The biggest benefit of immutability in React is when build simple pure components 



6. Functional Components
* We'll also change onClick={() => props.onClick()} to just onClick={props.onClick}
* Passing down the function is enough 
* Not that onClick={props.onClick()} would not work - it would call the function immediately instead of passing it down. 
1. Why did we have to change the function for the functional component 



7. 

