# React 2 

> # React - Conditional Rendering

***Conditional rendering in React works the same way conditions work in JavaScript.***

## Element Variables  

**can use variables to store elements. This can help you conditionally render a part of the component while the rest of the output doesn’t change.**

## Inline If with Logical && Operator  

**You may embed expressions in JSX by wrapping them in curly braces. This includes the JavaScript logical && operator.**

    function Mailbox(props) {
    const unreadMessages = props.unreadMessages;
    return (
        <div>
        <h1>Hello!</h1>
        {unreadMessages.length > 0 &&        <h2>          You have {unreadMessages.length} unread messages.        </h2>      }    </div>
    );
    }

    const messages = ['React', 'Re: React', 'Re:Re: React'];
    ReactDOM.render(
    <Mailbox unreadMessages={messages} />,
    document.getElementById('root')
    );

## Inline If-Else with Conditional Operator  

**Another method for conditionally rendering elements inline is to use the JavaScript conditional operator condition ? true : false.**

    render() {
    const isLoggedIn = this.state.isLoggedIn;
    return (
        <div>
        The user is <b>{isLoggedIn ? 'currently' : 'not'}</b> logged in.    </div>
    );
    }

## Preventing Component from Rendering 

**In rare cases you might want a component to hide itself even though it was rendered by another component. To do this return null instead of its render output.**

> # React - Lists & Keys

## Rendering Multiple Components  


**You can build collections of elements and include them in JSX using curly braces {}.**

    ReactDOM.render(
    <ul>{listItems}</ul>,  document.getElementById('root')
    );

## Basic List Component  

**Usually you would render lists inside a component.**

    function NumberList(props) {
    const numbers = props.numbers;
    const listItems = numbers.map((number) =>
        <li key={number.toString()}>      {number}
        </li>
    );
    return (
        <ul>{listItems}</ul>
    );
    }

    const numbers = [1, 2, 3, 4, 5];
    ReactDOM.render(
    <NumberList numbers={numbers} />,
    document.getElementById('root')
    );

## Keys  

**Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity.**

**The best way to pick a key is to use a string that uniquely identifies a list item among its siblings.**

## Extracting Components with Keys 

**Keys only make sense in the context of the surrounding array.**

## Keys Must Only Be Unique Among Siblings 

**Keys used within arrays should be unique among their siblings. However, they don’t need to be globally unique.**

**Keys serve as a hint to React but they don’t get passed to your components. If you need the same value in your component, pass it explicitly as a prop with a different name.**

> # React - Forms

## Controlled Components 

**In HTML, form elements such as (input), (textarea), and (select) typically maintain their own state and update it based on user input. In React, mutable state is typically kept in the state property of components, and only updated with setState().**

**With a controlled component, the input’s value is always driven by the React state.**

## The textarea Tag 

**In React, a (textarea) uses a value attribute instead.**

## The select Tag 

**You can pass an array into the value attribute, allowing you to select multiple options in a select tag.**

## Handling Multiple Inputs  

**When you need to handle multiple controlled input elements, you can add a name attribute to each element and let the handler function choose what to do based on the value of event.target.name.**

## Alternatives to Controlled Components 

**It can sometimes be tedious to use controlled components, because you need to write an event handler for every way your data can change and pipe all of the input state through a React component. 

> # React - Lifting State

## Adding a Second Input 

    const scaleNames = {  c: 'Celsius',  f: 'Fahrenheit'};
    class TemperatureInput extends React.Component {
    constructor(props) {
        super(props);
        this.handleChange = this.handleChange.bind(this);
        this.state = {temperature: ''};
    }

    handleChange(e) {
        this.setState({temperature: e.target.value});
    }

    render() {
        const temperature = this.state.temperature;
        const scale = this.props.scale;    return (
        <fieldset>
            <legend>Enter temperature in {scaleNames[scale]}:</legend>        <input value={temperature}
                onChange={this.handleChange} />
        </fieldset>
        );
    }
    }

## Writing Conversion Functions 

    function tryConvert(temperature, convert) {
    const input = parseFloat(temperature);
    if (Number.isNaN(input)) {
        return '';
    }
    const output = convert(input);
    const rounded = Math.round(output * 1000) / 1000;
    return rounded.toString();
    }

## Lifting State Up 

    class TemperatureInput extends React.Component {
    constructor(props) {
        super(props);
        this.handleChange = this.handleChange.bind(this);
        this.state = {temperature: ''};  }

    handleChange(e) {
        this.setState({temperature: e.target.value});  }

    render() {
        const temperature = this.state.temperature;    // ...  

**In React, sharing state is accomplished by moving it up to the closest common ancestor of the components that need it. This is called “lifting state up”.**

> # React - Composition vs Inheritance

## Containment 

**Some components don’t know their children ahead of time. This is especially common for components like Sidebar or Dialog that represent generic “boxes”.**

    function WelcomeDialog() {
    return (
        <FancyBorder color="blue">
        <h1 className="Dialog-title">        Welcome      </h1>      <p className="Dialog-message">        Thank you for visiting our spacecraft!      </p>    </FancyBorder>
    );
    }

## Specialization 

**Sometimes we think about components as being “special cases” of other components. For example, we might say that a WelcomeDialog is a special case of Dialog.**

    function Dialog(props) {
    return (
        <FancyBorder color="blue">
        <h1 className="Dialog-title">
            {props.title}
        </h1>
        <p className="Dialog-message">
            {props.message}
        </p>
        {props.children}    </FancyBorder>
    );
    }

    class SignUpDialog extends React.Component {
    constructor(props) {
        super(props);
        this.handleChange = this.handleChange.bind(this);
        this.handleSignUp = this.handleSignUp.bind(this);
        this.state = {login: ''};
    }

    render() {
        return (
        <Dialog title="Mars Exploration Program"
                message="How should we refer to you?">
            <input value={this.state.login}               onChange={this.handleChange} />        <button onClick={this.handleSignUp}>          Sign Me Up!        </button>      </Dialog>
        );
    }

    handleChange(e) {
        this.setState({login: e.target.value});
    }

    handleSignUp() {
        alert(`Welcome aboard, ${this.state.login}!`);
    }
    }

> # Thinking in React

## Start With A Mock 

> **Step 1: Break The UI Into A Component Hierarchy**

![](https://reactjs.org/static/9381f09e609723a8bb6e4ba1a7713b46/90cbd/thinking-in-react-components.png)

*italicized the data each component represents.*

1. FilterableProductTable (orange): contains the entirety of the example
2. SearchBar (blue): receives all user input
3. ProductTable (green): displays and filters the data collection based on user input
4. ProductCategoryRow (turquoise): displays a heading for each category
5. ProductRow (red): displays a row for each product

*Components that appear within another component in the mock should appear as a child in the hierarchy:*

* FilterableProductTable
***SearchBar***
**ProductTable**
*ProductCategoryRow*
*ProductRow*

> **Step 2: Build A Static Version in React**

*To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props. props are a way of passing data from parent to child.*

*State is reserved only for interactivity, that is, data that changes over time. Since this is a static version of the app, you don’t need it.*

> **Step 3: Identify The Minimal (but complete) Representation Of UI State**

*To build your app correctly, you first need to think of the minimal set of mutable state that your app needs.*

*Figure out the absolute minimal representation of the state your application needs and compute everything else you need on-demand.*

*Think of all the pieces of data in our example application.*

* The original list of products
* The search text the user has entered
* The value of the checkbox
* The filtered list of products

*Ask three questions about each piece of data:*

* Is it passed in from a parent via props? If so, it probably isn’t state.
* Does it remain unchanged over time? If so, it probably isn’t state.
* Can you compute it based on any other state or props in your component? If so, it isn’t state.

> **Step 4: Identify Where Your State Should Live**

*React is all about one-way data flow down the component hierarchy. It may not be immediately clear which component should own what state.*

*For each piece of state in your application:*

* Identify every component that renders something based on that state.
* Find a common owner component.
* Either the common owner or another component higher up in the hierarchy should own the state.
* If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

*Let’s run through this strategy for our application:*

* ProductTable needs to filter the product list based on state and SearchBar needs to display the search text and checked state.
* The common owner component is FilterableProductTable.
* It conceptually makes sense for the filter text and checked value to live in FilterableProductTable

> **Step 5: Add Inverse Data Flow**

*built an app that renders correctly as a function of props and state flowing down the hierarchy. support data flowing the other way: the form components deep in the hierarchy need to update the state in FilterableProductTable.*

*React makes this data flow explicit to help you understand how your program works, but it does require a little more typing than traditional two-way data binding.*