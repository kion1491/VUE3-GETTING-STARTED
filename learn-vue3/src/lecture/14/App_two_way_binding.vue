<template>
  <div>
    <h2>input value</h2>
    <!-- <input
      type="text"
      :value="inputValue"
      @input="(event) => (inputValue = event.target.value)"
    /> -->
    <input type="text" v-model="inputValue" />
    <div>{{ inputValue }}</div>

    <hr />

    <h2>textarea value</h2>
    <textarea v-model="textareaValue" name="" id=""></textarea>
    <div>{{ textareaValue }}</div>

    <hr />

    <h2>checkbox value</h2>
    <label for="checkbox">{{ checkboxValue }}</label>
    <input
      type="checkbox"
      id="checkbox"
      v-model="checkboxValue"
      true-value="yes"
      false-value="no"
    />
    <!-- <input
      type="checkbox"
      name=""
      id="checkbox"
      :checked="checkboxValue"
      @change="(event) => (checkboxValue = event.target.checked)"
    /> -->

    <h2>checkbox values</h2>
    <label>
      <input type="checkbox" value="html" v-model="checkboxValues" />
      html
    </label>
    <label>
      <input type="checkbox" value="css" v-model="checkboxValues" />
      css
    </label>
    <label>
      <input type="checkbox" value="js" v-model="checkboxValues" />
      js
    </label>

    <div>
      {{ checkboxValues }}
    </div>

    <hr />

    <h2>radio value</h2>
    <label>
      <input type="radio" name="type" value="O" v-model="radioValue" />
      O형
    </label>
    <label>
      <input type="radio" name="type" value="A" v-model="radioValue" />
      A형
    </label>
    <div>
      {{ radioValue }}
    </div>

    <hr />

    <h2>select value</h2>
    <select v-model="selectValue">
      <option value="html">html</option>
      <option value="css">css</option>
      <option value="javascript">javascript</option>
    </select>
    <div>
      {{ selectValue }}
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const inputValue = ref("");
    const textareaValue = ref("");
    const checkboxValue = ref(true);
    const checkboxValues = ref([]);
    const radioValue = ref("O");
    const selectValue = ref("html");
    return {
      inputValue,
      textareaValue,
      checkboxValue,
      radioValue,
      selectValue,
      checkboxValues,
    };
  },
};
</script>

<style lang="scss" scoped></style>
