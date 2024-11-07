<template>
  <div>
    <p>author: {{ author }}</p>
    <p>title: {{ title }}</p>
  </div>
</template>

<script>
import { reactive, toRef, toRefs } from "vue";

export default {
  setup() {
    const book = reactive({
      author: "kion",
      year: "2024",
      title: "vue3 toRefs",
      description: "vue3 toRefs, toRef를 공부하자",
      price: "무료",
    });

    // const { author, title } = toRefs(book);
    const author = toRef(book, "author");
    const title = toRef(book, "title");
    return { author, title, book };
  },
};
</script>

<style lang="scss" scoped></style>
