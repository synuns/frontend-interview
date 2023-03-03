# Stack과 Queue

## Stack 직접 구현하기

```js
class Stack {
  constructor() {
    this.items = [...arguments];
    this.length = arguments.length;
  }
  push() {
    this.items.push(...arguments);
    this.length += arguments.length;
  }
  pop() {
    if(this.items.length === 0) {
      return 'Underflow';
    }
    this.length -= 1;
    return this.items.pop();
  }
  peek() {
    if(this.length === 0){
      return 'None';
    }
    return this.items[this.length -1]
  }
  isEmpty() {
    return this.length === 0;
  }
}
```

**Usage**

```js
const stack = new Stack(1, 2, 3);
stack.push(4, 5);
stack.pop();
stack.peek();
stack.isEmpty();
console.log(stack.length);
```

## Queue 직접 구현하기

```js
class Queue {
  constructor() {
    this.items = [...arguments];
    this.length = arguments.length;
  }
  enqueue() {
    this.items.push(...arguments);
    this.length += arguments.length;
  }
  dequeue() {
    if(this.items.length === 0) {
      return 'Underflow';
    }
    this.length -= 1;
    return this.items.shift();
  }
  front() {
    if(this.length === 0){
      return 'None';
    }
    return this.items[0]
  }
  isEmpty() {
    return this.length === 0;
  }
}
```

**Usage**

```js
const queue = new Queue(1, 2, 3);
queue.enqueue(4, 5);
queue.dequeue();
queue.front();
queue.isEmpty();
console.log(queue.length);
```