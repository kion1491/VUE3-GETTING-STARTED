<template>
  <div>
    <div id="modifiers">
      <div @click="clickDiv">
        DIVDIV
        <p @click.self="clickP">
          PPPPPP
          <!-- <span @click.stop="clickSpan">SPAN SPAN</span> -->
          <span @click="clickSpan">SPAN SPAN</span>

          <a href="https://naver.com" @click.prevent.stop="clickA">click A</a>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    const clickDiv = () => {
      console.log("clickDiv");
    };
    const clickP = () => {
      console.log("clickP");
    };
    const clickSpan = () => {
      console.log("clickSpan");
    };
    const clickA = (e) => {
      alert("clickA!!");
    };
    return { clickDiv, clickP, clickSpan, clickA };
  },
};
</script>

<style scoped>
#modifiers div,
#modifiers p,
#modifiers span {
  padding: 40px;
}
#modifiers div {
  background-color: #ccc;
}
#modifiers p {
  background-color: #999;
}

#modifiers span {
  background-color: #666;
  display: block;
}
</style>
