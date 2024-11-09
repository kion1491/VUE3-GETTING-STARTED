<template>
  <div>
    <div class="text" :class="[classObject, specialClass]">텍스트입니다.</div>
    <button v-on:click="toggle">TOGGLE</button>
    <button v-on:click="toggleDanger">TOGGLE Danger</button>
  </div>
</template>

<script>
import { computed, reactive, ref } from "vue";
export default {
  setup() {
    const isActive = ref(true);
    const toggle = () => {
      isActive.value = !isActive.value;
    };
    // const classObject = reactive({
    //   active: true,
    //   "text-danger": true,
    // });

    const classObject = computed(() => {
      return {
        active: true && true,
        "text-danger": true && true,
      };
    });

    const specialClass = ref("specialClass");

    const hasError = ref(false);
    const toggleDanger = () => {
      hasError.value = !hasError.value;
    };
    return {
      isActive,
      toggle,
      hasError,
      toggleDanger,
      classObject,
      specialClass,
    };
  },
};
</script>

<style scoped>
.text-danger {
  color: red;
}
</style>
