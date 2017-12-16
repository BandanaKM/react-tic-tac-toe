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