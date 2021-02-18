<template>
  <div id="app">
    <Count />
    <FindName />
  </div>
</template>

<script>
import Count from "./components/Count";
import FindName from './components/FindName';


export default {
  name: "App",
  components: {
    Count,
    FindName
  }
};
</script>

<style>
  body {
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  }
</style>
