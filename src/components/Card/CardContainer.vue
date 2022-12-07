<!-- eslint-disable prettier/prettier -->
<script setup>
import FigureCard from "./components/FigureCard.vue";
import StatsCard from "./components/StatsCard.vue";
import HeadingCard from "./components/HeadingCard.vue";
const props = defineProps({
  data: Object,
});
</script>

<template>
  <section class="container">
    <FigureCard
      :imgUrl="props.data?.sprites.other.dream_world.front_default"
      :imgAlt="props.data?.name"
      :imgCaption="props.data?.name"
      :expBase="props.data?.base_experience"
    ></FigureCard>
    <StatsCard :stats="props.data?.stats"></StatsCard>
    <HeadingCard :heading="props.data?.abilities"></HeadingCard>
  </section>
</template>

<style scoped>
.container {
  display: grid;
  grid-template-columns: 1.5fr repeat(2, 1fr);
  grid-template-rows: repeat(2, 1fr);
  gap: 0px 10px;
  width: 100%;
  max-width: 725px;
  grid-auto-flow: row;
  align-items: center;
  background: #fafafa;
  border-radius: 25px;
  padding: 1rem;
  grid-template-areas:
    "image stats stats"
    "image habilities habilities";
}
</style>
