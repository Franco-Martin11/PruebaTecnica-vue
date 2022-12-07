<!-- eslint-disable prettier/prettier -->
<script setup>
import FigureCard from "./components/FigureCard.vue";
import DescriptionContainer from './components/DescriptionContainer.vue'
const props = defineProps({
  data: Object,
});
</script>

<template>
  <section class="container">
    <DescriptionContainer :pokemon="{
      name: props.data?.name,
      expBase: props.data?.base_experience,
    }" :stats="{ stats: props.data?.stats, abilities: props.data?.abilities }"></DescriptionContainer>
    <FigureCard :imgUrl="props.data?.sprites.other.dream_world.front_default" :imgAlt="props.data?.name"
      :type="props.data?.types"></FigureCard>
  </section>
</template>

<style scoped>
.container {
  display:flex;
  gap: 0px 10px;
  width: 100%;
  max-width: 725px;
  grid-auto-flow: row;
  align-items: center;
  background: #fafafa;
  border-radius: 25px;
  padding: 1rem;
}

@media screen and (max-width:550px) {
  .container{
    flex-wrap: wrap-reverse;
  justify-content: center;
  padding:.5rem;
  }
}
</style>
