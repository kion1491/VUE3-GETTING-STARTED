<template>
  <main>
    <div class="container py-4">
      <div class="container text-center">
        <div class="row g-5">
          <div class="col col-4">
            <AppCard></AppCard>
          </div>
          <div class="col col-4">
            <AppCard></AppCard>
          </div>
          <div class="col col-4">
            <AppCard></AppCard>
          </div>
          <div class="col col-4">
            <AppCard></AppCard>
          </div>
          <div class="col col-4">
            <AppCard></AppCard>
          </div>
          <div class="col col-4">
            <AppCard></AppCard>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import AppCard from "./AppCard.vue";

console.log("AppCard Module 동작");

export default {
  components: {
    AppCard: AppCard,
  },
  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
