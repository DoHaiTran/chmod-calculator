<template>
  <div id="app">
    <Calculator></Calculator>
    <!-- <PermissionMonitor></PermissionMonitor> -->
    <!-- <PermissionItem></PermissionItem> -->
  </div>
</template>

<script>
 import Calculator from "@/components/Calculator"
//import PermissionMonitor from './components/PermissionMonitor.vue'
//import PermissionItem from './components/PermissionItem.vue'
export default {
  name: 'App',
  components: {
    Calculator
    //PermissionItem
    //PermissionMonitor
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
