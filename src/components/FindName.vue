<template>
  <div class="find">
    <hr />
    <h4>Surask mano vardą:</h4>
    <input type="text" @input="findingName = $event.target.value" />
    <p>Viso vardų: {{ names.length }}, sutapimų: {{ filterNames.length }}</p>
    <ul v-for="(name, index) in filterNames" :key="index">
      <li>{{ name }}</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'FindName',
  data() {
    return {
      findingName: '',
      names: ['Jonas', 'Petras', 'Antanas', 'Kazys', 'Vaclovas', 'Gintautas'],
    };
  },
  computed: {
    filterNames() {
      return this.names.filter((name) =>
        name.toLowerCase().includes(this.findingName.toLowerCase()),
      );
    },
  },
};
</script>
<style></style>
