<template>
  <div>
    <p>
      ENTER 키에만 반응시킬때 이런 방법도 있다: if (event.key === "Enter")
      <br />
      하지만, @keyup.enter를 사용해도 된다!
      <br />
      또한 @keyup.enter.ctrl 이런식으로 입력하면, 다중키 입력만 받을수도 있다!
    </p>
    <input type="text" @keyup.enter.ctrl="addTodo" />
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{ todo }}
      </li>
    </ul>
  </div>
</template>

<script>
import { reactive } from "vue";

export default {
  setup() {
    const todos = reactive([]);

    const addTodo = (event) => {
      /* ENTER 키에만 반응시킬때 이런 방법도 있다. */
      /* 하지만, @keyup.enter를 사용해도 된다! */

      // if (event.key === "Enter") {
      //   todos.push(event.target.value);
      // }

      todos.push(event.target.value);
    };
    return { todos, addTodo };
  },
};
</script>

<style lang="scss" scoped></style>
