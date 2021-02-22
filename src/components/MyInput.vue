<template>
        <input type="text" class="search" @input="$emit('input', $event.target.value)">
</template>
<script>
export default {
    name: "MyInput",
    model: {
        prop: "value",
        event: "input"
    }
}
</script>
<style>
  .search {
    margin: 0 10px;
    width: 250px;
    padding: 5px;
    border-radius: 5px;
    border: 1px solid lightgray;
}
</style>