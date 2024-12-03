Storybook.js is a development tool for building, testing, and documenting UI components in isolation. It provides an interactive interface to:

- **Visualize components** in different states.
- **Test components** independently of the app.
- **Document usage** for teams or clients.

#### Installation and run

```bash 
npx storybook@latest init
npm run storybook
```

## 1. **Writing Stories**

A "story" describes a specific use case for a component. It is typically written in a `*.stories.js` or `*.stories.tsx` file.

#### **Basic Story Example**

```tsx
import React from 'react';
import { Button } from './Button';

export default {
  title: 'Components/Button', // Storybook category
  component: Button,         // The component to render
};

export const Primary = () => <Button label="Primary" primary />;
export const Secondary = () => <Button label="Secondary" />;
```

#### **Key Elements**

- **`title`**: Organizes the component in Storybook’s sidebar.
- **`component`**: Specifies which component is being documented.
- **Named Exports**: Each export represents a different variation of the component.

## **2. Adding Controls**

Controls allow users to interactively modify a component's props in the Storybook UI.
- **`argTypes`**: Defines controls for props.
- **`args`**: Provides default values for the story.

#### **Example with Controls**

```tsx
import React from 'react';
import { Button } from './Button';

export default {
  title: 'Components/Button',
  component: Button,
  argTypes: {
    label: { control: 'text' },  // Makes 'label' editable
    primary: { control: 'boolean' }, // Toggle for 'primary' prop
  },
};

const Template = (args) => <Button {...args} />;

export const Primary = Template.bind({});
Primary.args = {
  label: 'Primary Button',
  primary: true,
};

export const Secondary = Template.bind({});
Secondary.args = {
  label: 'Secondary Button',
  primary: false,
};
```