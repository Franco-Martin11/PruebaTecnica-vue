<template>
  <article class="description__container">
    <div class="heading__container">
      <h1>{{ pokemon.name }}</h1>
      <h2>{{ pokemon.expBase }}<span class="exp__star"> ★</span></h2>
    </div>

    <div class="stats__container">
      <StatsCard :stats="stats.stats"></StatsCard>
      <AbilitiesCard :heading="stats.abilities"></AbilitiesCard>
    </div>
  </article>
</template>

<script>
import AbilitiesCard from "./AbilitiesCard.vue";
import StatsCard from "./StatsCard.vue";
export default {
  props: {
    pokemon: Object,
    stats: Object,
    heading: Array,
  },
  components: { AbilitiesCard, StatsCard },
};
</script>

<style scoped>
.description__container {
  display: flex;
  flex-direction: column;
  gap: 10px;
  padding: 10px;
}

.heading__container {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 15px;
  text-transform: capitalize;
}

.stats__container {
  display: flex;
  flex-direction: row;
  gap: 10px;
}

.exp__star {
  color: bisque;
}
</style>
