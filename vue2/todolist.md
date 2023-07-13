# todolist

```jsx
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .completed {
      text-decoration: line-through;
      color: grey;
    }
  </style>
</head>
<body>
  <div id="app">
    <h1>Todo List</h1>
    <input type="text" v-model="content">
    <button @click="addTodo">+</button>
    <ul>
      <li v-for="todo in todoList">
        <input type="checkbox" @click="toggleTodo(todo)"> <span :class="{ completed: todo.completed }">{{ todo.content }}</span>
      </li>
    </ul>
    <button @click="deleteTodo">완료 목록 삭제</button>
  </div>
  <script src="https://cdn.jsdelivr.net/npm/vue@2.7.14/dist/vue.js"></script>
  <script>
    const app = new Vue({
      el: '#app',
      data: {
        content: '',
        todoList: [],
      },
      methods: {
        addTodo(event) {
          if(this.content !== '')  {
            const newTodo = {
              content: this.content,
              completed: false,
            }
            this.todoList.push(newTodo)
            this.content = ''
          } else {
            alert('내용을 입력해 주세요!!!!')
          }
        },
        deleteTodo() {
          this.todoList = this.todoList.filter((todo) => !todo.completed)
        },
        toggleTodo(todo){
          todo.completed = !todo.completed
        }
      }
    })
  </script>
</body>
</html>
```