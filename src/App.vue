<script>
import CardContainer from "./components/Card/CardContainer.vue";
import { useFetch } from "./api/ApiService";
import ButtonPagination from "./components/ButtonPagination.vue";
export default {
  name: "App",
  data() {
    return { counter: 1, response: null };
  },
  created() {
    const { data, error } = useFetch(
      `https://pokeapi.co/api/v2/pokemon/${this.counter}`
    );
    error.value ? console.error(error) : (this.response = data);
  },
  watch: {
    counter(newValue) {
      const { data, error } = useFetch(
        `https://pokeapi.co/api/v2/pokemon/${newValue}`
      );
      error.value ? console.error(error) : (this.response = data);
    },
  },
  methods: {
    increse: function () {
      this.counter += 1;
    },
    decrese: function () {
      this.counter -= 1;
    },
  },
  components: { CardContainer, ButtonPagination },
};
</script>

<template>
  <main class="main__container">
    <CardContainer :data="response"></CardContainer>
    <ButtonPagination
      :methods="{ increse, decrese, counter }"
    ></ButtonPagination>
  </main>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}

.main__container {
  display: grid;
  place-content: center;
  justify-items: center;
  min-height: 100vh;
  gap: 1rem;
  background: rgba(0, 0, 0, 0.074);
  padding: 1rem 0.25rem;
}
</style>
