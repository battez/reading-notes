# Components
Almost everything in React consists of components, which can be 
1. class components or 
2. simple components.

Most React apps have many small components, and everything loads into the main App component. Components also often get their own file, so let’s change up our project to do so.

Convention: custom class component. We capitalize custom components to differentiate them from regular HTML elements. 

**A class component must include render(), and the return can only return one parent element**.

The other type of component in React is the simple component, which is a function. This component doesn’t use the class keyword.

    const TableHeader = () => { 
    return (

**components can be nested in other components, and simple and class components can be mixed**.


## separate container comps from presentation component
if a component has to have state, make calculations based on props, or manage any other complex logic, then that component **shouldn't** also have to render HTML-like JSX.

Instead of rendering HTML-like JSX, the component should render another component. It should be that component's job to render HTML-like JSX.

A presentation component will get rendered by a container component:
i.e. 
    Containers/ --container.js will render components/--pres-component.js

or i.e. export class GuineaPigs extends React.Component { 
gets rendered by GunieaPigsContainer . NB "export" is required to do this.

### stateless functional component. 
Stateless functional components have some advantages over typical component classes. 

If you have a component class with nothing but a render function, then you can rewrite that component class in a very different way. Instead of using React.Component, you can write it as JavaScript function!

- Stateless functional components usually have props passed to them.

- To access these props, give your stateless functional component a parameter. This parameter will automatically be equal to the component's props object.

- It's customary to name this parameter props. 


    export const MyComponentClass = (props) => {
      return <h1>{props.title}</h1>;
    }

- They emphasize the fact that components are basically functions! 
- A component takes two optional inputs, props and state, and outputs HTML and/or other components

## Props
One of the big deals about React is how it handles data, and it does so with properties, referred to as props, and with state. However the component cannot change the props – they’re read-only. (This is where State comes in).

React handles data like this with virtualDOM: you’ll see the array of data in the property. The data that’s stored here is known as the virtual DOM, which is a fast and efficient way of syncing data with the actual DOM. 

ES6 property shorthand to create a variable that contains this.props.characterData:

    const { characterData } = this.props;


## State

You can think of state as any data that should be saved and modified without necessarily being added to a database – for example, adding and removing items from a shopping cart before confirming your purchase.


