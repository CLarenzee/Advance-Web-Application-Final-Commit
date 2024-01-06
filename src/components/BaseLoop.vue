<template>
    <div>
      <label for="newTask">New Task:</label>
      <input type="text" id="newTask" v-model="newTask">
      <button @click="addTask">Add Task</button>
  
      <div class="task-list">
        <h2>Task List</h2>
        <ul>
          <li v-for="(task, index) in tasks" :key="index">
            {{ task }}
            <button @click="deleteTask(index)">Delete</button>
          </li>
        </ul>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newTask: '',
        tasks: [],
      };
    },
    methods: {
      addTask() {
        if (this.newTask.trim() !== '') {
          this.tasks.push(this.newTask.trim());
          this.newTask = '';
        }
      },
      deleteTask(index) {
        this.tasks.splice(index, 1);
      },
    },
  };
  </script>
  
  <style scoped>
  .task-list {
    margin-top: 20px;
  }
  </style>
  