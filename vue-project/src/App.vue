<script setup>

  import { ref } from 'vue'

  const newTask = ref('')
  const tasks = ref([])
  let nextId = 1

  function addTask() {

    const text = newTask.value.trim()

    if( !text ) return
    tasks.value.push({ id: nextId++, text })
    newTask.value = ''

  }

  function removeTask(id) {

    tasks.value = tasks.value.filter(
      t => t.id !== id
    )

  }

</script>

<template>

  <h2>Task list</h2>

  <form @submit.prevent="addTask">

    <input v-model="newTask" placeholder="New task.." />
    <button type="submit">Add</button>

  </form>

  <ul>

    <li v-for="task in tasks" :key="task.id">
      {{ task.text }}
      <button @click="removeTask(task.id)">remove</button>
    </li>

  </ul>

  <p v-if="tasks.length === 0">No tasks yet</p>

</template>