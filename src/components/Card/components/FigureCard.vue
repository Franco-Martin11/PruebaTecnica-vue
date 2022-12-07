<template>
  <figure class="">
    <img loading='lazy' :src="imgUrl" :alt="imgAlt" />
    <figcaption class="type__container">
      <span class="type__heading">Type:</span>
      <span class="type__item" v-for="typePokemon of type" :key="typePokemon.slot">{{ typePokemon.type.name }}</span>
    </figcaption>
  </figure>
</template>

<script>
export default {
  props: {
    imgUrl: String,
    imgAlt: String,
    type: Array,
  },
};
</script>

<style scoped>
figure {
  grid-area: image;
}

.type__container {
  display: flex;
  justify-content: center;
  gap: 10px;
  text-transform: capitalize;
}

.type__heading {
  font-weight: 500;
}

img {
  height: 200px;
  width: 200px;
}

.name {
  text-align: center;
  text-transform: capitalize;
}

.subtitle {
  text-align: center;
}
</style>
