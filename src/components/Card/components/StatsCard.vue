<template>
  <div v-if="stats !== null" class="container__stats">
    <h3>Stats:</h3>
    <span v-for="(items, index) of stats" v-bind:key="index">
      <span class=""> {{ items.stat.name }}: </span>
      {{ items.base_stat }}
    </span>
  </div>
</template>

<script>
export default {
  props: {
    stats: Array,
  },
};
</script>

<style scoped>
.container__stats {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  width: 100%;
  grid-area: stats;
}

span {
  text-transform: capitalize;
}
</style>
