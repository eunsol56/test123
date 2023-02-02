<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Hello Vue 3.0 + Vite" /> -->
  <Login/>
  <TimeTable/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TimeTable from './components/TimeTable.vue'
import Login from './components/Login.vue'

export default {
  name: 'App',
  components: {
    TimeTable,Login
  }
}
</script>
