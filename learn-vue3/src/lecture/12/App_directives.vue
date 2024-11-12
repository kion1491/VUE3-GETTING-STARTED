<template>
  <div>
    <span>{{ msg }}</span> <br />
    <span v-text="msg"></span> <br />

    <hr />

    <span v-html="htmlMsg"></span> <br />
    <span v-text="htmlMsg"></span>

    <hr />

    <p v-once>{{ msg }} !! v-once이다!!!</p>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const msg = ref("안녕하세요");
    const htmlMsg = ref("<span>Hello!</span>");
    return { msg, htmlMsg };
  },
};
</script>

<style lang="scss" scoped></style>
