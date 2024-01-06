<template>
    <div>
      <h3>My Task List</h3>
      <ul>
        <li v-for="(task, index) in tasks" :key="index">
          {{ task.title }}
          <button @click="removeTask(index)">Remove</button>
        </li>
      </ul>
      <input v-model="newTask" @keyup.enter="addTask" placeholder="Add a new task">
      <button @click="addTask">Add Task</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        tasks: [],
        newTask: ''
      };
    },
    methods: {
      addTask() {
        if (this.newTask.trim()) {
          this.tasks.push({ title: this.newTask });
          this.newTask = '';
        }
      },
      removeTask(index) {
        this.tasks.splice(index, 1);
      }
    }
  };
  </script>
  
  <style>
  /* Add your styles here */
  </style>
  