# Exp-5 Develop a complete Todo application with all features.
## AIM:
To create react app to develop a complete Todo application with all features.
## PROCEDURE:
### STEP 1:
Create react app by npm create-react-app.
### STEP 2:
Make changes to app.js and create new file todolist.js where the todo app works.
### STEP 3:
Include Style in the react using app.css and import it to todolist.js.
### STEP 4:
Verify the output by running the Web-Layout in any web browser. 
## PROGRAM:
### App.css
```css
.App {
  text-align: center;
  margin-top: 2rem;
}

.todo-container {
  width: 400px;
  margin: 0 auto;
}

.todo-title {
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

.todo-form {
  display: flex;
  justify-content: space-between;
  margin-bottom: 1rem;
}

.todo-input {
  flex-grow: 1;
  padding: 0.5rem;
  font-size: 1rem;
}

.todo-button {
  background-color: #4caf50;
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  font-size: 1rem;
  cursor: pointer;
}

.todo-list {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

.todo-item {
  display: flex;
  align-items: center;
  background-color: #f2f2f2;
  padding: 0.5rem;
  margin-bottom: 0.5rem;
}

.todo-text {
  flex-grow: 1;
  margin-left: 0.5rem;
}

.todo-delete {
  color: red;
  margin-left: 0.5rem;
  cursor: pointer;
}
```
### App.js
```js
import React from 'react';
import TodoList from './TodoList';

function App() {
  return (
    <div className="App">
      <h1>Todo List</h1>
      <TodoList />
    </div>
  );
}
export default App;
```
### App.test.js
```js
import { render, screen } from '@testing-library/react';
import App from './App';

test('renders learn react link', () => {
  render(<App />);
  const linkElement = screen.getByText(/learn react/i);
  expect(linkElement).toBeInTheDocument();
});
```
### index.css
```css
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, 'Courier New',
    monospace;
}
```
### index.js
```js
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
```
### TodoList.js
```js
import React, { useState } from 'react';
import './App.css';

const TodoList = () => {
  const [todos, setTodos] = useState([]);
  const [newTodo, setNewTodo] = useState('');

  const addTodo = () => {
    if (newTodo.trim() !== '') {
      setTodos([...todos, { text: newTodo }]);
      setNewTodo('');
    }
  };

  const deleteTodo = (index) => {
    const updatedTodos = todos.filter((_, i) => i !== index);
    setTodos(updatedTodos);
  };

  return (
    <div className="todo-container">
      <h2 className="todo-title">Todo List</h2>

      <div className="todo-form">
        <input
          type="text"
          value={newTodo}
          onChange={(e) => setNewTodo(e.target.value)}
          className="todo-input"
        />
        <button onClick={addTodo} className="todo-button">
          Add Todo
        </button>
      </div>

      <ul className="todo-list">
        {todos.map((todo, index) => (
          <li key={index} className="todo-item">
            <span className="todo-text">{todo.text}</span>
            <span
              className="todo-delete"
              onClick={() => deleteTodo(index)}
            >
              Delete
            </span>
          </li>
        ))}
      </ul>
    </div>
  );
};

export default TodoList;
```
## OUTPUT:
![image](https://github.com/Karthikeyan21001828/MERN_EX05/assets/93427303/59bb6ea9-28d9-4c78-94fe-774c49b1196f)

## RESULT:
React app to develop a complete Todo application with all features has been created and output has been verified.
