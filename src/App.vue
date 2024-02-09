<template>
  <TgSqanQrPage/>
</template>


<script>
import TgSqanQrPage from "@/components/TgSqanQrPage";
export default {
  name: 'App',
  components: {TgSqanQrPage},
  data() {
  },
  setup() {
    // console.log("setup")
    // window.Telegram.WebApp.showScanQrPopup()
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
  background: black;
}

.item {
  background: red;
  /*display: block;*/
  /*min-width: 200px;*/
  /*max-width: 250px;*/
  width: 200px;
  height: 300px;
  margin: 10px;
}

.list {
  /*max-width: content-box;*/
  width: 100%;
  display: grid;
  /*grid-template-columns: minmax();*/
  /*flex-wrap: wrap;*/
  /*justify-content: ;*/
  background: gray;
}

.wrap {
  /*display: table;*/
  /*min-width: 0;*/
  /*justify-content: start;*/
}
</style>
