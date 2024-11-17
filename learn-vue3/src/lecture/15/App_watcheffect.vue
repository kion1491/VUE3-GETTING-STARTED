<template>
  <div>
    <form @submit.prevent="saveFunc(title, contents)">
      <input type="text" v-model.lazy="title" placeholder="Title" />
      <textarea
        v-model.lazy="contents"
        placeholder="Contents"
        name=""
        id=""
        cols="30"
        rows="10"
      ></textarea>

      <hr />

      <button>SAVE</button>
    </form>
  </div>
</template>

<script>
import { ref, watchEffect } from "vue";
export default {
  setup() {
    const title = ref("");
    const contents = ref("");
    const saveFunc = (title, contents) => {
      console.log("저장되었습니다. title: ", title, ", contents: ", contents);
    };
    watchEffect(() => {
      console.log(title.value);
      console.log(contents.value);
      saveFunc(title.value, contents.value);
    });

    return { title, contents, saveFunc };
  },
};
</script>

<style lang="scss" scoped></style>
