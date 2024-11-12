<template>
  <div>
    <h3>
      v-memo를 통해 지정해준 속성이 변경될 때만 다른 모든 속성들도 함께 최신화가
      됨.
    </h3>

    <div v-memo="[subscribers]">
      <p>subscribers: {{ subscribers }}</p>
      <p>views: {{ views }}</p>
      <p>likes: {{ likes }}</p>
    </div>
    <button @click="subscribers++">subscribers ++</button>
    <button @click="views++">views ++</button>
    <button @click="likes++">likes ++</button>
    <div>
      <p>subscribers: {{ subscribers }}</p>
      <p>views: {{ views }}</p>
      <p>likes: {{ likes }}</p>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const subscribers = ref(4000);
    const views = ref(400);
    const likes = ref(200);

    return { subscribers, views, likes };
  },
};
</script>

<style lang="scss" scoped></style>
