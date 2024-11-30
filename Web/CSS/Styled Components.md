### 1. **Styled Components** 

Styled Components allow you to define and attach styles directly to a component, using tagged template literals. The styles are scoped to the component, preventing them from affecting other parts of your application. 
### Syntax:
```jsx
import styled from 'styled-components';

const Button = styled.button`
  background-color: blue;
  color: white;
  font-size: 16px;
  border-radius: 5px;

  &:hover {
    background-color: darkblue;
  }
`;

function App() {
  return <Button>Click Me</Button>;
}
```

### 2. **Props in Styled Components**

You can pass props to styled components and use them to dynamically change styles.

```jsx
const Button = styled.button`
  background: transparent;

  ${props => props.$primary && css`
    background: #BF4F74;
    color: white;
  `}
`;

const Container = styled.div`
  text-align: center;
`

export function Component({ children, className, $primary, ...props }) {
	return (
	<>
		<Button className={className} $primary={$primary} {...props}>{children}</Button>
		<Container></Container>
	</>
	)
}

render(
  <Container>
    <Button>Normal Button</Button>
    <Button $primary>Primary Button</Button>
  </Container>
);
```