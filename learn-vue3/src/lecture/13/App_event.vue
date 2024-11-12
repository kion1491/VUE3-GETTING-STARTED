<template>
  <div>
    <button @click="printEventInfo('Hello vue3', $event)">
      inline event handler
    </button>

    <hr />

    <input type="text" @keyup="onKeyupHandler" />
  </div>
</template>

<script>
export default {
  setup() {
    const printEventInfo = (message, event) => {
      console.log("message: ", message);
      console.log("event.target: ", event.target);
      console.log("event.target: ", event.target.tagName);
    };

    const onKeyupHandler = (event) => {
      console.log("onKeyupHandler", event.key);
    };
    return { printEventInfo, onKeyupHandler };
  },
};
</script>

<style lang="scss" scoped></style>
