## 📘 What is AJAX?

**AJAX** (Asynchronous JavaScript and XML) is a technique for making asynchronous requests to a server without reloading the entire page.

> Modern AJAX often uses **JSON** instead of XML, but the name remains.

---

## 💡 Why Use AJAX?

- Update parts of a webpage without refreshing
    
- Improve user experience with faster interactions
    
- Send/receive data in the background
    
- Reduce server load
    

---

## 🔧 How AJAX Works

1. **Event triggers** (e.g., button click)
    
2. **JavaScript** creates an `XMLHttpRequest` or uses `fetch()`
    
3. Request sent to the **server**
    
4. **Server processes** and sends back data (JSON, XML, HTML, text)
    
5. JavaScript updates the **DOM** dynamically
    

---

## 🛠️ Using `fetch()` (Modern AJAX)

```js
fetch('/api/data')
  .then(response => response.json())
  .then(data => {
    console.log('Data received:', data);
    document.getElementById('result').innerText = data.message;
  })
  .catch(error => console.error('Error:', error));
```

---

## 🛠️ Using `XMLHttpRequest` (Legacy)

```js
const xhr = new XMLHttpRequest();
xhr.open('GET', '/api/data', true);
xhr.onload = function () {
  if (xhr.status === 200) {
    const data = JSON.parse(xhr.responseText);
    console.log(data);
  }
};
xhr.send();
```

---

## 🌐 Example: AJAX with a Form

```html
<form id="myForm">
  <input type="text" name="name" placeholder="Enter name">
  <button type="submit">Submit</button>
</form>
<div id="result"></div>

<script>
document.getElementById('myForm').addEventListener('submit', function(e) {
  e.preventDefault();
  const formData = new FormData(this);

  fetch('/api/submit', {
    method: 'POST',
    body: formData
  })
    .then(res => res.json())
    .then(data => {
      document.getElementById('result').innerText = data.message;
    });
});
</script>
```

---

## ✅ Summary

- AJAX lets you interact with a server **without reloading the page**
    
- Use `fetch()` for a modern, promise-based approach
    
- Data is often sent/received in **JSON**
    
- Great for **search suggestions**, **form submissions**, **live updates**