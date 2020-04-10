---
layout: post
title:      "Dispatching Actions Using mapDispatchToProps in Redux"
date:       2020-04-10 19:59:46 +0000
permalink:  dispatching_actions_using_mapdispatchtoprops_in_redux
---


Redux is a library that work separate from react, which it holds our application data in one central store. Redux allows all components in our React application to get access to our application state. Using Redux allow us having clearly process of how to read or change data from the state. In order to make change in the state we have to create an action that describe the change that we need to make. There are many ways we can use to connect these actions. One way is “mapDispatchToProps” function.  

mapDispatchToProps” function allows us to bundling our actions and dispatch into prop so we can call them from our component. If we want to make a change to state such as add new record or delete existing one we need to dispatch an action from the component. Bellow an example shows how to dispatch an action to delete a tool:  

```
const mapDispatchToProps = dispatch => {
  return {
	
    // dispatching plain actions
		deleteTool:  (id) => { dispatch({type: ‘DELETE_TOOL’,  id: id}) }
		
  }
}

```

The above function maps our dispatch to props by taking in dispatch as an argument and then returns an object that contain a function.  Then we need to pass mapDispatchToProps function as the second argument into connect :

```
export default connect(mapStateToProps, mapDispatchToProps)(Tool);
```
