<template>
  <article class="article__container">
    <h3 class="article__heading">Abilities:</h3>
    <div class="stats__container">
      <div v-for="(items, index) in heading" :key="index">
        <h2>{{ items.ability.name }} : {{ items.slot }}★</h2>
      </div>
    </div>
  </article>
</template>

<script>
export default {
  props: {
    heading: Array,
  },
};
</script>

<style scoped>
.article__container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  grid-area: habilities;
}

.article__heading {
  text-align: start;
  width: 100%;
}

.stats__container {
  display: flex;
  flex-direction: row;
  gap: 1rem;
  flex-wrap: wrap;
  width: 100%;
  justify-content: space-between;
}

.stats__container > div {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 1rem;
  align-items: flex-end;
  text-transform: capitalize;
}

.stats__container > div > h2 {
  font-size: 18px;
}

.ability__slot {
  font-size: 16px;
  font-weight: 300;
}
</style>
