<template>
  <div class="button__container">
    <button
      v-if="methods.counter > 1"
      class="slide"
      @click="methods.decrese"
      type="button"
    >
      <div>Prev</div>
      <span class="icon">←</span>
    </button>

    <h4>{{ methods.counter }}</h4>

    <button class="slide" @click="methods.increse" type="button">
      <div>Next</div>
      <span class="icon">→</span>
    </button>
  </div>
</template>

<script>
export default {
  props: {
    methods: Object,
  },
};
</script>

<style>
.button__container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  gap: 1rem;
}

.slide {
  font-size: 20px;
  font-weight: 200;
  letter-spacing: 1px;
  padding: 13px 30px 13px;
  outline: 0;
  border: 1px solid black;
  cursor: pointer;
  position: relative;
  background-color: rgba(0, 0, 0, 0);
}

.slide .icon {
  opacity: 0;
  font-size: 28px;
  transition: 0.2s;
  position: absolute;
  right: 10px;
  top: 21px;
  transition: transform 1;
}

.slide div {
  transition: transform 0.8s;
}

.slide:hover div {
  transform: translateX(-6px);
}

.slide::after {
  content: "";
  background-color: #66f2d5;
  width: 100%;
  z-index: -1;
  position: absolute;
  height: 100%;
  top: 7px;
  left: 7px;
}

.slide:hover .icon {
  opacity: 1;
  transform: translateX(-6px);
}
</style>
