<template>
  <figure class="">
    <img :src="imgUrl" :alt="imgAlt" />
    <figcaption>
      <h1 class="name">{{ imgCaption }}</h1>
    </figcaption>
    <h5 class="subtitle">Base Expercience : {{ expBase }}★</h5>
  </figure>
</template>

<script>
export default {
  props: {
    imgUrl: String,
    imgCaption: String,
    imgAlt: String,
    expBase: Number,
  },
};
</script>

<style scoped>
figure {
  grid-area: image;
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
