# React lifecycle 

![Diagram](https://miro.medium.com/max/2800/0*0saPKFiTUk6W3FYp) 

> Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’ ? 

***Based off the diagram the ‘render’ happens before the  ‘componentDidMount’.*** 

> What is the very first thing to happen in the lifecycle of React ? 

***The Render phase*** 

> Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Updates :- 

1. Constructor.
1. Render.
1. React Updates. 
1. ComponentDidMount. 
1. ComponentWillUnmount.

> What does componentDidMount do ?

***This method is invoked immediately after a component is mounted. If you need to load anything using a network request or initialize the DOM, it should go here. This method is a good place to set up any subscriptions.*** 

*Example :-* 

     componentDidMount() {
     console.log(‘got videos’);
     this.getVideos(‘cats’);
     }
     getVideos(query) {
     var options = {
     key: this.props.YOUTUBE_API_KEY,
     query: query
     }; 

## <https://www.youtube.com/watch?v=IYvD9oBCuJI>

> What types of things can you pass in the props ?

***Props are pass into the component.***


> What is the big difference between props and state ?

* Props pass into a component. 

* Props is handled outside of that component.

* Props is update it outside the component.

* State is handled inside of that component.

* State is update it inside the component.

> When do we re-render our application ?

***Based on something the user has done. *** 


> What are some examples of things that we could store in state ? 

***Based on user input :***

* Input Elements. 

* Check Box. 

* Select Box. 