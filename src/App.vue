<template>
<!--  <MyComponent/>-->
  <FullBoxComponent/>
</template>
<script>
// import HelloWorld from './components/HelloWorld.vue'
// import MyComponent from "@/components/MyComponent";


import FullBoxComponent from "@/components/FullBoxComponent";

export default {
  name: 'App',
  components: {
    // MyComponent
    FullBoxComponent
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
