<template>
  <div></div>
</template>

<script>
import { reactive, ref } from "vue";

export default {
  setup() {
    // ref -> Object: 끌어다 쓸 때, .value를 안붙여도 된다!
    const count = ref(0);
    const state = reactive({
      count: count,
    });

    count.value++;
    count.value++;
    // console.log(count.value);
    // console.log("state.count: ", state.count);

    // ref -> Array : 끌어다 쓰려면, .value를 붙여야 한다!
    const message = ref("Hello");
    const arr = reactive([message]);
    console.log("state.count: ", arr[0].value);
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
