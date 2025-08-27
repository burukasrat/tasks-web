<script setup>
import { useTasksStore } from '@/stores/tasksStore';

const store = useTasksStore();
let newTask = {completed: false};
</script>

<template>
    <div class="add-task">
        <h3>Add a new task</h3>
        <label for="title">Title *</label>
        <input v-model="newTask.name" type="text" name="title" placeholder="Enter a title..."><br />
        <label for="description">Description *</label>
        <textarea v-model="newTask.description" name="description" rows="4" placeholder="Enter a description..." /><br />
        <button class="btn gray" @click="store.addTask(newTask)">Add Task</button>
    </div>
</template>

<style lang="scss" scoped>
  .add-task {
    margin-top: 60px;

    input, textarea {
      width: 360px;
      max-width: 100%;
      margin-top: 12px;
      padding: 5px;
    }

    button {
      width: 360px;
      margin-top: 12px;
    }
  }
</style>