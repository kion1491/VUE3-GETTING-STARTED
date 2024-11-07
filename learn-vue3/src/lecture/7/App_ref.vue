<template>
  <div>
    <p>
      reactive는 직접 값을 넣지 말고 객체로써 반환 시켜줘야지 반응형으로
      동작한다. 이것이 바로 ref와의 차이점!
    </p>
    <p>{{ message.value }}</p>
    <button v-on:click="addMessage">add click</button>
  </div>

  <hr />

  <div>
    <p>
      ref는 그냥 refMessage로 넣어줘도 된다. 그리고 const로 선언해줘도 된다.
      반응형 그냥 된다.
    </p>
    <p>{{ refMesseage }}</p>
    <button v-on:click="refAddMessage">add click</button>
  </div>
</template>

<script>
import { reactive, ref } from "vue";

export default {
  setup() {
    // reactive는 직접 값을 넣지 말고 객체로써 반환 시켜줘야지 반응형으로 동작한다. 이것이 바로 ref와의 차이점!
    let message = reactive({
      value: "Hello Vue!",
    });
    const addMessage = () => {
      message.value = message.value + "!";
    };

    let refMesseage = ref("Hello Ref!");
    const refAddMessage = () => {
      refMesseage.value = refMesseage.value + "!";
    };
    return {
      message,
      addMessage,
      refMesseage,
      refAddMessage,
    };
  },
};
</script>

<style lang="scss" scoped></style>
