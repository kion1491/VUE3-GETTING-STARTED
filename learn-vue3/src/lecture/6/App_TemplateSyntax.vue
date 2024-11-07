<template>
  <div>
    <h2>보간법(일회성으로만 보관하는 방법: v-once)</h2>
    <p>{{ message }}</p>
    <p v-once>{{ message }}</p>
    <button v-on:click="message = message + '!'">Click</button>

    <hr />

    <h2>rawHtml 사용</h2>
    <p>{{ rawHtml }}</p>
    <p v-html="rawHtml"></p>

    <hr />

    <h2>속성 바인딩</h2>
    <p>v-bind: 는 그냥 : 로만 사용해도 된다. 워낙 자주 쓰여서 이렇게 해줬다.</p>
    <div v-bind:title="dynamicTitle">마우스 올리면 설명이 뜸</div>
    <div :title="dynamicTitle">마우스 올리면 설명이 뜸</div>
    <input type="text" value="홍길동" v-bind:disabled="isInputDisabled" />

    <p>
      v-bind는 모든 필요한 속성, 속성값을 객체형태로 받아와서 한방에 넣어 줄수도
      있다.
    </p>
    <input v-bind="attrInput" />

    <hr />

    <h2>JavaScript</h2>
    {{ message.split("").reverse().join("") }}<br />
    {{ isInputDisabled ? "예" : "아니오" }}
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const message = ref("안녕하세요!");
    const rawHtml = ref("<strong>안녕하세요</strong>");

    const dynamicTitle = ref("마우스 올리면 뜨는 설명!");

    const isInputDisabled = ref(false);

    const attrInput = ref({
      type: "text",
      value: "12345678",
      disabled: false,
    });

    return {
      message,
      rawHtml,
      dynamicTitle,
      isInputDisabled,
      attrInput,
    };
  },
};
</script>

<style lang="scss" scoped></style>
