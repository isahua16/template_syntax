<template>
  <div id="app">
    <menu-items></menu-items>
  </div>
</template>

<script>
  import MenuItems from '@/components/MenuItems.vue'

export default {
  name: 'App',
  components: {
    MenuItems
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
