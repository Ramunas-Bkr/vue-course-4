<template>
  <div class="root">
    <p>Įveskite produktų kiekį</p>
    <div class="product-count-block">
      <button @click="changeCount(-1)">-</button>
      <input :value="count" type="number" />
      <button @click="changeCount(1)">+</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "MyComponent",
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
.product-count-block button {
  background: #6ed111;
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
  font-weight: 700;
  color: #000;
}
.product-count-block input {
  margin: 0 10px;
  width: 50px;
  text-align: center;
  padding: 5px 0;
  border-radius: 5px;
}
</style>
