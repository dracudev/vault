## 🔄 The Node.js Event Loop

The **event loop** is a fundamental part of how Node.js works.

Node.js uses a **single-threaded** model with **event-driven**, **non-blocking I/O**. This is made possible through the event loop.

### 🧩 What is the Event Loop?

The event loop is what allows Node.js to perform **non-blocking I/O operations** — despite being single-threaded — by **offloading operations** to the system kernel or internal thread pool when possible.

### 🕰️ Phases of the Event Loop

1. **Timers**: executes `setTimeout()` and `setInterval()` callbacks
    
2. **Pending Callbacks**: executes I/O callbacks deferred to the next loop
    
3. **Idle, Prepare**: only used internally
    
4. **Poll**: retrieve new I/O events; execute I/O-related callbacks
    
5. **Check**: execute `setImmediate()` callbacks
    
6. **Close Callbacks**: e.g., `socket.on('close', ...)`
    

Each phase has a **FIFO queue** of callbacks to execute.

### 🧵 Example of the Event Loop

```
setTimeout(() => {
  console.log("Timeout callback");
}, 0);

setImmediate(() => {
  console.log("Immediate callback");
});

console.log("Synchronous log");
```

**Expected output**:

```
Synchronous log
Immediate callback
Timeout callback
```

> Note: the order of `setImmediate` and `setTimeout` can vary depending on the environment and execution context.

### 📊 Visual Representation (Simplified)

```
┌───────────────────────────┐
│      Call Stack           │
└────────────┬──────────────┘
             ↓
     ┌────────────────┐
     │  Event Queue   │ ← setTimeout, etc.
     └────────────────┘
             ↓
       Event Loop
             ↓
     Executes callbacks
```

---

## ✅ Summary

- Node.js runs JavaScript outside the browser
    
- Uses event loop & asynchronous I/O for performance
    
- Built on the V8 engine (used in Chrome)
    
- Includes powerful built-in modules
    
- Uses `npm` to manage packages
    
- The **event loop** is key to Node.js's non-blocking I/O model