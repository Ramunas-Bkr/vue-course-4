<template>
  <div id="app">
    <Count />
    <FindName />
    <hr>
    <PhotoRedactor />
    <hr>
    <product-list />
  </div>
</template>

<script>
import Count from "./components/Count";
import FindName from './components/FindName';
import PhotoRedactor from './components/PhotoRedactor.vue';
import ProductList from './components/ProductList.vue';


export default {
  name: "App",
  components: {
    Count,
    FindName,
    PhotoRedactor,
    ProductList
  }
};
</script>

<style>
  body {
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  }
  button {
  background: #6ed111;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  font-weight: 700;
  color: #fff;
  }
  li {
    list-style: none;
  }
</style>
