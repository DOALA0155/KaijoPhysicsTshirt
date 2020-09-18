<template>
  <div class="typing-view">
    <div class="typing-view-content" id="typing">
      <VueTyper text="Kaijo Physics Club" erase-style="clear"></VueTyper>
    </div>
  </div>
</template>

<script>
import { VueTyper } from 'vue-typer';
export default {
  data() {
    return {
      scrollY: 0
    }
  },
  components: {
    VueTyper
  },
  methods: {
    get_scroll_y: function () {
      var scroll_top = window.scrollY
      this.fade_in_out(scroll_top)
    },
    fade_in_out: function (scroll_top) {
      var typing_text = document.getElementById("typing")

      if (scroll_top >= (window.innerHeight * 2)) {
        typing_text.style.opacity = 0
      } else {
        typing_text.style.opacity = 1
      }
    }
  },
  mounted() {
    window.addEventListener('scroll', this.get_scroll_y);
  },
  beforeDestroy() {
    window.addEventListener('scroll', this.get_scroll_y);
  }
}
</script>

<style scoped>
@media (min-width: 600px) {
  div.typing-view {
    width: 100vw;
    height: 300vh;
    position: relative;
  }
  div.typing-view div.typing-view-content {
    height: 6vw;
    width: 80vw;
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    margin: auto;
    text-align: center;
    transition: all 0.5s ease-out;
  }
  div.typing-view div.typing-view-content span {
    font-size: 3vw;
    line-height: 6vw;
    font-weight: bold;
    font-family:"Yu Gothic", "游ゴシック", YuGothic, "游ゴシック体", "ヒラギノ角ゴ Pro W3", "メイリオ", sans-serif;
  }
}
</style>