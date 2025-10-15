### Next.js: Create a Static Blog Post Page (getStaticProps)

```
// pages/posts.js
export async function getStaticProps() {
  const res = await fetch('https://jsonplaceholder.typicode.com/posts?_limit=5');
  const posts = await res.json();
  return { props: { posts } };
}

export default function Posts({ posts }) {
  return (
    <div>
      <h2>Blog Posts</h2>
      <ul>
        {posts.map(post => <li key={post.id}>{post.title}</li>)}
      </ul>
    </div>
  );
}

```

### Redux: Simple Todo List (Redux Toolkit)
```
// store.js
import { configureStore, createSlice } from '@reduxjs/toolkit';

const todoSlice = createSlice({
  name: 'todos',
  initialState: [],
  reducers: {
    addTodo: (state, action) => { state.push({ text: action.payload }); }
  }
});

export const { addTodo } = todoSlice.actions;

export const store = configureStore({ reducer: { todos: todoSlice.reducer } });

// TodoList.js
import React, { useState } from "react";
import { useSelector, useDispatch } from "react-redux";
import { addTodo } from "./store";

function TodoList() {
  const [input, setInput] = useState("");
  const todos = useSelector(state => state.todos);
  const dispatch = useDispatch();

  return (
    <div>
      <input value={input} onChange={e => setInput(e.target.value)} />
      <button onClick={() => { dispatch(addTodo(input)); setInput(""); }}>
        Add Todo
      </button>
      <ul>
        {todos.map((todo, i) => <li key={i}>{todo.text}</li>)}
      </ul>
    </div>
  );
}

export default TodoList;
// store.js
import { configureStore, createSlice } from '@reduxjs/toolkit';

const todoSlice = createSlice({
  name: 'todos',
  initialState: [],
  reducers: {
    addTodo: (state, action) => { state.push({ text: action.payload }); }
  }
});

export const { addTodo } = todoSlice.actions;

export const store = configureStore({ reducer: { todos: todoSlice.reducer } });

// TodoList.js
import React, { useState } from "react";
import { useSelector, useDispatch } from "react-redux";
import { addTodo } from "./store";

function TodoList() {
  const [input, setInput] = useState("");
  const todos = useSelector(state => state.todos);
  const dispatch = useDispatch();

  return (
    <div>
      <input value={input} onChange={e => setInput(e.target.value)} />
      <button onClick={() => { dispatch(addTodo(input)); setInput(""); }}>
        Add Todo
      </button>
      <ul>
        {todos.map((todo, i) => <li key={i}>{todo.text}</li>)}
      </ul>
    </div>
  );
}

export default TodoList;
```
