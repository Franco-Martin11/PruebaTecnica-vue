<script>
// import CardContainer from "./components/Card/CardContainer.vue";
export default {
  name: "App",
  data() {
    return { counter: 1, response: null };
  },

  created() {
    fetch(`https://pokeapi.co/api/v2/pokemon/${this.counter}`)
      .then((res) => res.json())
      .then((res) => (this.response = res))
      .catch((error) => {
        console.log(error);
      });
  },
  watch: {
    counter(newValue) {
      fetch(`https://pokeapi.co/api/v2/pokemon/${newValue}`)
        .then((res) => res.json())
        .then((res) => (this.response = res))
        .catch((error) => {
          console.log(error);
        });
    },
  },
  methods: {
    increse: function () {
      this.counter += 1;
    },
  },
};
</script>

<template>
  <h1>esto es una prueba a ver si es que funciona</h1>

  <h4 v-if="response !== null">{{ response.name }}</h4>
  <div class="containerpadre" v-if="response">
    <div class="container" v-for="pokemons in response" :key="pokemons.id">
      <h3>{{ pokemons.name }}</h3>
    </div>
  </div>
  <button @click="increse">nose si esto va a funcionar</button>
  <h1>{{ counter }}</h1>
</template>

<style scoped>
.pruba {
  display: flex;
}
</style>
