<template>
  <div class="main">
    <TypingView></TypingView>
    <TshirtView></TshirtView>
  </div>
</template>

<script>
import TypingView from "~/components/TypingView.vue";
import TshirtView from "~/components/TshirtView.vue";

export default {
  components: {
    TypingView,
    TshirtView
  }
}
</script>

<style scoped>
div.main {
  width: 100vw;
}
</style>
