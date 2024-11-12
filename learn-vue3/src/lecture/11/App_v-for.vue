<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item.id">
        {{ item.message }}
      </li>
    </ul>

    <p>index 도 출력!</p>
    <ul>
      <li v-for="(item, index) in items" :key="item.id">
        {{ index }}: {{ item.message }}
      </li>
    </ul>

    <p>
      item.id가 짝수인 경우만 출력하려면? ( = 조건문 + for문 조합해서 쓰려면?)
    </p>
    <h3>방법1: template사용</h3>
    <template v-for="(item, index) in items" :key="item.id">
      <ul>
        <li v-if="item.id % 2 == '0'">
          ID: {{ item.id }}, 인덱스: {{ index }}, {{ item.message }}
        </li>
      </ul>
    </template>
    <h3>방법2: computed사용</h3>
    <template v-for="(item, index) in evenItems" :key="item.id">
      <ul>
        <li v-if="item.id % 2 == '0'">
          ID: {{ item.id }}, 인덱스: {{ index }}, {{ item.message }}
        </li>
      </ul>
    </template>
  </div>

  <hr />
  <h3>객체를 이렇게 풀어줄수도 있다.</h3>
  <ul>
    <li v-for="(value, key, index) in myObject" :key="key">
      {{ index }} - {{ key }} = {{ value }}
    </li>
  </ul>
</template>

<script>
import { computed, reactive } from "vue";

export default {
  setup() {
    const items = reactive([
      { id: 1, message: "Java" },
      { id: 2, message: "Python" },
      { id: 3, message: "C#" },
      { id: 4, message: "C" },
    ]);
    const evenItems = computed(() => items.filter((item) => item.id % 2 == 0));

    const myObject = reactive({
      title: "김또롱",
      author: "kion",
      publishedAt: "2024-01-01",
    });

    return { items, evenItems, myObject };
  },
};
</script>

<style lang="scss" scoped></style>
