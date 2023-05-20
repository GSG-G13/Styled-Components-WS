# **styled-components <💅>**

ReactJS styled-components is a library that allows you to write CSS code in your JavaScript files using a component-based approach. It provides a convenient way to create and manage styled-components, encapsulating both the styling and the logic within a single component, making it easier to develop and maintain styling in React applications.

---
## **Why styled-components?**
- **Automatic critical CSS:** styled-components keeps track of which components are rendered on a page and injects their styles and nothing else, fully automatically. Combined with code splitting, this means your users load the least amount of code necessary.
- **No class name bugs:** styled-components generates unique class names for your styles. You never have to worry about duplication, overlap or misspellings.
- **Simple dynamic styling:** adapting the styling of a component based on its props or a global theme is simple and intuitive without having to manually manage dozens of classes.
---
## **Installation**

```javascript
// with npm
npm install styled-components

// with yarn
yarn add styled-components
```
---
## **Getting Started!**
This example creates Fout simple components, a wrapper, a title, a description, and a Writer, with some styles attached to them:
```javascript
// Import styled-components library to use it in the code
import styled from 'styled-components';

// Create a Wrapper component that'll render a <div> tag with some styles
const Wrapper = styled.div`
  width: 400px;
  height: fit-content;
  border-radius: 15px;
  padding: 1rem;
  background-color: pink;
  margin: 5rem auto;
`;

// Create a Title component that'll render an <h1> tag with some styles
const Title = styled.h3`
  color: #0000ffb0;
  font-size: 2rem;
  margin-bottom: 0.5rem;
`;

// Create a Description component that'll render an <p> tag with some styles
const Description = styled.p`
  color: #fff;
  font-size: 1.1rem;
  margin-bottom: 0.5rem;

  // Nesting components
  span{
    color: green;
    font-weight: bold;
  }
  &:hover span{
    color: yellow
  } 
`;

// Extending all of Description component styles and adding extra styles. 
const ExtraDescription = styled(Description)`
  font-size: 0.975rem;
`;

// Create a Writer component that'll render an <span> tag with some styles
const Writer = styled.span`
  font-size: 0.8rem;
  color: #999;
`;

const ContactButton = styled.button`
  border: 1px solid #000;
  background-color: none;
  outline: none;
  cursor: pointer;
  padding: 0.5rem 1rem;
  color: #000;
  margin-left: 230px;
  display: inline-block;

  &:hover{
    background-color: #ccc;
  }
`;

// Use Title, Wrapper and etc... like any other React component – except they're styled!
const Header = () => {
  return (
    <Wrapper>
      <Title>Hello G13!</Title>
      <Description>
        You are welcome in react <span>styled-components</span> session 
      </Description>
      <hr />
      <ExtraDescription><span>ReactJS styled-components</span> is a library that allows you to write CSS code in your JavaScript files</ExtraDescription>
      <hr />
      <Writer>Ahmed Osama</Writer>
      <ContactButton>Contact</ContactButton>
    </Wrapper>
  )
}
```
![](https://hackmd.io/_uploads/ry2HiprSh.png)

> ***Note:*** When naming styled-components you must use PascalCase for components names:
**SubmitButton**, **HeadWrapper**, **JobTitle**

![](https://hackmd.io/_uploads/BkkKohrHh.png)

---

## **Passed props**
In ReactJS styled-components, you can pass props to customize the styles of your components. Here's an example of how you can pass props to a styled component:

```javascript
import styled from 'styled-components';

// Styled component with props
const Message = styled.div`
  background-color: ${props => props.type === 'error' ? 'red' : 'green'};
  color: white;
  padding: 10px;
`;

// Usage of the styled component
const UserMessage = () => {
  return (
    <div>
      <Message type="error">Error Message</Message>
      <Message type="success">Success Message</Message>
    </div>
  );
}
```
![](https://hackmd.io/_uploads/ryvwA6Hr2.png)

---
## **Attaching additional props**

The `attrs` method in styled-components provides a convenient way to set default attributes and values for your styled components. It allows you to define a set of attributes and their default values using a function that receives the props as an argument.

The `attrs` function receives the props as an argument, and it returns an object where each key represents an attribute, and its value is the default value for that attribute.

```javascript
import styled from 'styled-components';

// Styled component with attrs
const Button = styled.button.attrs(props => ({
  type: 'button',
  disabled: props.disabled || false,
}))`
  background-color: ${props => props.primary ? 'blue' : 'gray'};
  color: white;
  padding: 10px 20px;
  border: none;
  cursor: ${props => props.disabled ? 'not-allowed' : 'pointer'};
`;

// Usage of the styled component
function App() {
  return (
    <div>
      <Button primary>Primary Button</Button>
      <Button disabled>Disabled Button</Button>
    </div>
  );
}
```

![](https://hackmd.io/_uploads/SkJ-ng8r2.png)

---
For More Information you can read styled-components documentation [styled-components](https://https://styled-components.com/docs/basics)

