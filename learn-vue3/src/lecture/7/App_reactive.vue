<template>
  <div>
    <button v-on:click="increment">Click {{ state.count }}</button>
  </div>
  <div>
    <button v-on:click="deepIncrement">Click {{ state.deep.deppCount }}</button>
  </div>
</template>

<script>
import { reactive } from "vue";

export default {
  setup() {
    const state = reactive({
      count: 0,
      deep: {
        deppCount: 0,
      },
    });

    const increment = () => {
      state.count++;
    };
    const deepIncrement = () => {
      state.deep.deppCount++;
    };
    return {
      state,
      increment,
      deepIncrement,
    };
  },
};
</script>

<style lang="scss" scoped></style>
