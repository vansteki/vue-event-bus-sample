<template>
  <div class="hello">
    <div>
      <input class="btn btn-light" type="button" value="到處看看" @click="lookAround">
    </div>
    <div>
      <input class="btn btn-dark" type="button" value="珍奶" @click="wanaDrink"> 
    </div>
    <green-button></green-button>
  </div>
</template>

<script>
import GreenButton from "./GreenButton";
import Bus from "../services/bus";

export default {
  name: "HelloWorld",
  components: {
    GreenButton
  },
  data() {
    return {
      msg: "Welcome to Your Vue.js App"
    };
  },
  methods: {
    lookAround() {
      Bus.$emit("到處看看");
    },
    wanaDrink() {
      alert("老闆：賣光囉～");
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
