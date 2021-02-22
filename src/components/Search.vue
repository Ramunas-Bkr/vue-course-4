<template>
  <div class="search flex">
    <input type="text" class="search" v-model="searchText" />
    <button type="button" @click="$emit('search', searchText)">
      Rasti
    </button>
  </div>
</template>
<script>
export default {
  name: 'search',
  data() {
      return {
          searchText: ""
      }
  },
};
</script>
<style></style>
