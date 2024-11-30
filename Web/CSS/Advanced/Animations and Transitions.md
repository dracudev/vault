### Transitions

```css
button {
  transition: background-color 0.3s ease-in-out;
}

button:hover {
  background-color: red;
}
```

### Animations

```css
@keyframes slidein {
  from {
    transform: translateX(0%);
  }
  to {
    transform: translateX(100%);
  }
}

div {
  animation: slidein 2s forwards;
}
```