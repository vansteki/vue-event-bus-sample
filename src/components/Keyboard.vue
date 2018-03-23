<template>
      <div class="keyboard-body">
        {{ this.price }} X {{ this.amount }} =  {{ this.price * this.amount }}
        <div>
          <div class="btn btn-primary" @click="setValue">1</div>
          <div class="btn btn-primary" @click="setValue">2</div>
          <div class="btn btn-primary" @click="setValue">3</div>
        </div>
        <div>
          <div class="btn btn-primary" @click="setValue">4</div>
          <div class="btn btn-primary" @click="setValue">5</div>
          <div class="btn btn-primary" @click="setValue">6</div>
        </div>
        <div>
          <div class="btn btn-primary" @click="setValue">7</div>
          <div class="btn btn-primary" @click="setValue">8</div>
          <div class="btn btn-primary" @click="setValue">9</div>
        </div>
    </div>
</template>

<script>
import Bus from "../services/bus";

export default {
  name: "Keyboard",
  data() {
    return {
      price: 0,
      amount: 0
    };
  },
  methods: {
    setValue(event) {
      this.amount = event.target.textContent * 1;
    }
  },
  mounted() {
    Bus.$on("greenButtonClicked", (item, price) => {
      this.price = price;
    });
    Bus.$on("到處看看", () => {
      this.price = 0;
      this.amount = 0;
    });
  }
};
</script>
<style scoped>
.btn {
  margin-top: 10px;
  margin-right: 10px;
}
</style>
