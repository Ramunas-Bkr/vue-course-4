<template>
  <div class="root">
    <h4>Įveskite produktų kiekį</h4>
    <div class="product-count-block">
      <button @click="changeCount(-1)">-</button>
      <input :value="count" type="number" />
      <button @click="changeCount(1)">+</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "Count",
  data() {
    return {
      count: 1
    };
  },
  methods: {
    changeCount(number) {
      if (this.count <= 1 && number === -1) {
        alert("Kiekis negali būti mažesnis už 1");
        return;
      } else if (this.count >= 10 && number === 1) {
        alert("Kiekis negali būti didesnis nei 10");
        return;
      } else {
        this.count = this.count + number;
      }
    }
  }
};
</script>
<style>
  .root {
    margin-bottom: 50px;
  }
  .product-count-block input {
    margin: 0 10px;
    width: 50px;
    text-align: center;
    padding: 5px 0;
    border-radius: 5px;
    border: 1px solid lightgray;
  }
</style>
