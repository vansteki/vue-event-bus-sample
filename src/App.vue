<template>
  <div id="app">
    <!-- <img width="25%" src="./assets/logo.png"> -->
    <HelloWorld/>
    <keyboard></keyboard>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import Keyboard from "./components/Keyboard";
import Bus from "./services/bus";

export default {
  name: "App",
  components: {
    HelloWorld,
    Keyboard
  },
  mounted() {
    // 監聽事件
    Bus.$on("greenButtonClicked", (item, price) => {
      alert(`老闆: ${item}只要${price}元！`);
    });
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
