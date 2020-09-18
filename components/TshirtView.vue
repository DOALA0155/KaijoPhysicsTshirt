<template>
  <div class="tshirt-view">
    <div class="tshirt-view-content">
      <div class="tshirt-image" id="image">
        <img :src="require('~/static/tshirt.png')">
      </div>
      <div class="tshirt-description" id="description">
        <span>海城中高物理部公式Tシャツです。</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      scrollY: 0
    }
  },
  methods: {
    get_scroll_y: function () {
      var scroll_top = window.scrollY
      this.fade_in_out(scroll_top)
    },
    fade_in_out: function (scroll_top) {
      var image = document.getElementById("image")
      var description = document.getElementById("description")

      if (scroll_top >= (window.innerHeight * 2.99)) {
        image.style.opacity = 1
        image.style.marginTop = 0
        description.style.opacity = 1
        description.style.marginTop = 0
      } else {
        image.style.opacity = 0
        image.style.marginTop = "2.5vw"
        description.style.opacity = 0
        description.style.marginTop = "5vw"
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
div.tshirt-view {
  width: 100vw;
  height: 55vw;
  position: relative;
}
div.tshirt-view div.tshirt-view-content {
  height: 50vw;
  width: 70vw;
  position: absolute;
  left: 0;
  right: 0;
  top: 5vw;
  margin: auto;
}
div.tshirt-view div.tshirt-view-content div.tshirt-image {
  width: 40vw;
  height: 40vw;
  position: absolute;
  left: 0;
  right: 0;
  margin: auto;
  transition: all 0.5s ease-out;
  margin-top: 2.5vw;
  opacity: 0;
}
div.tshirt-view div.tshirt-view-content div.tshirt-image img {
  width: 40vw;
}
div.tshirt-view div.tshirt-view-content div.tshirt-description {
  width: 70vw;
  height: 4vw;
  position: absolute;
  left: 0;
  right: 0;
  bottom: 8vw;
  margin: auto;
  text-align: center;
  transition: all 0.5s ease-out;
  margin-top: 5vw;
  opacity: 0;
}
div.tshirt-view div.tshirt-view-content div.tshirt-description span {
  font-size: 2vw;
  line-height: 4vw;
  font-weight: bold;
  font-family:"Yu Gothic", "游ゴシック", YuGothic, "游ゴシック体", "ヒラギノ角ゴ Pro W3", "メイリオ", sans-serif;
}
</style>