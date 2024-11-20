<template>
  <main>
    <div class="container py-4">
      <div class="container text-center">
        <div class="row g-5">
          <div v-for="post in posts" :key="post.id" class="col col-4">
            <AppCard
              :title="post.title"
              :contents="post.contents"
              :type="post.type"
              :is-like="post.isLike"
              @toggle-like="post.isLike = !post.isLike"
            ></AppCard>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import { reactive } from "vue";
import AppCard from "./AppCard.vue";

console.log("AppCard Module 동작");

export default {
  components: {
    AppCard: AppCard,
  },
  setup() {
    const cardCont = reactive({
      title: "제목2",
      contents: "내용2",
    });
    const posts = reactive([
      { id: 1, title: "제목2", contents: "내용2", isLike: true, type: "news" },
      { id: 2, title: "제목3", contents: "내용3", isLike: true, type: "news" },
      { id: 3, title: "제목4", contents: "내용4", isLike: true, type: "news" },
      {
        id: 4,
        title: "제목5",
        contents: "내용5",
        isLike: false,
        type: "notice",
      },
      {
        id: 5,
        title: "제목6",
        contents: "내용6",
        isLike: false,
        type: "notice",
      },
    ]);
    return { cardCont, posts };
  },
};
</script>

<style lang="scss" scoped></style>
