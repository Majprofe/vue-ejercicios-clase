<script setup>
  import { ref } from 'vue'
  const name = ref('John Doe')
  const status = ref(true)
  const status2 = ref('active')
  const tasks = ref(['task1', 'task2', 'task3'])
  const link = ref('https://www.google.com')
  const toggleStatus = () => {
    //Para poder acceder a un valor reactivo tenemos que poner .value
    if (status2.value === 'active') {
      status2.value = 'pending'
    } else {
      status2.value = 'active'
    }
    
  }

</script>
<template>
  <h1> {{ name }}</h1>
  <!--v-if-->
  <p v-if="status">User is active</p>
  <p v-else>User is inactive</p>
  <p v-if="status2 === 'active'">Second user active</p>
  <p v-else>Second user inactive</p>
  <h3>Tasks:</h3>
  <ul>
  <!--v-for-->
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>
  <!--v-bind-->
  <a v-bind:href="link">Google</a>
    <!--<a :href="link">Google</a>-->
  <!--v-on-->
  <br/>
  <button v-on:click="toggleStatus">Change Status</button>
<!--   <button @:click="toggleStatus">Change Status</button>
 -->

</template>

<style scoped>

</style>
