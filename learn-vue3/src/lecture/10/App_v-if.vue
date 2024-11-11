<template>
  <div>
    <h2 v-if="visible">true 입니다.</h2>
    <h2 v-else>false 입니다.</h2>
    <button v-on:click="visible = !visible">toggle button</button>

    <p>template을 이용해서, 조건문 하나로 여러개의 태그들을 묶을 수도 있다.</p>
    <template v-if="visible">
      <h1>Title</h1>
      <p>test</p>
      <p>paragraph</p>
    </template>

    <hr />

    <button v-on:click="type = 'A'">A button</button>
    <button v-on:click="type = 'B'">B button</button>
    <button v-on:click="type = 'C'">C button</button>
    <button v-on:click="type = 'D'">D button</button>
    <h3 v-if="type === 'A'">A 입니다.</h3>
    <h3 v-else-if="type === 'B'">B 입니다.</h3>
    <h3 v-else-if="type === 'C'">C 입니다.</h3>
    <h2 v-else>A, B, C가 아닙니다.</h2>

    <hr />

    <p>
      v-show: 엘리먼트 상에서는 존재하고, displat none 처리만 해줌. 이것이 v-if
      와의 차이점!
    </p>
    <h1 v-show="ok">v-show title 입니다.</h1>
    <button v-on:click="ok = !ok">v-show toggle button</button>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const visible = ref(true);
    const type = ref("A");

    const ok = ref(true);

    return { visible, type, ok };
  },
};
</script>

<style lang="scss" scoped></style>
