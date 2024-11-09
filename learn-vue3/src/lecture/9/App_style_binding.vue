<template>
  <div>
    <div :style="styleObject">
      Lorem Ipsum is simply dummy text of the printing and typesetting industry.
      Lorem Ipsum has been the industry's standard dummy text ever since the
      1500s, when an unknown printer took a galley of type and scrambled it to
      make a type specimen book. It has survived not only five centuries, but
      also the leap into electronic typesetting, remaining essentially
      unchanged. It was popularised in the 1960s with the release of Letraset
      sheets containing Lorem Ipsum passages, and more recently with desktop
      publishing software like Aldus PageMaker including versions of Lorem
      Ipsum.
    </div>
    <button v-on:click="fontSize--">-</button>
    <button v-on:click="fontSize++">+</button>
  </div>
</template>

<script>
import { computed, reactive, ref } from "vue";
export default {
  setup() {
    // const styleObject = reactive({
    //   color: "red",
    //   fontSize: "13px",
    // });

    const fontSize = ref(13);
    const styleObject = computed(() => {
      return {
        color: "red",
        fontSize: fontSize.value + "px",
      };
    });
    return { styleObject, fontSize };
  },
};
</script>

<style lang="scss" scoped></style>
