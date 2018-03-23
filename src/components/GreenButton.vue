<template>
  <div>
    <input class="btn btn-success" type="button" :value="this.item" @click="calc">  
  </div>
</template>

<script>
// load Bus instance
// import { default as Bus } from "../services/bus";
import Bus from "../services/bus";

export default {
  name: "GreenButton",
  data() {
    return {
      item: "巨大花野菜"
    };
  },
  methods: {
    calc() {
      // 送出自定義的事件，並傳入一個參數 10(價格)，監聽到這個事件的對象也會收到這個參數
      Bus.$emit("asdasd", this.item, 100);
    }
  }
};
</script>
