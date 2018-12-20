<template>
  <div class="container">
    <!--相册封面-->
    <div class="cover"  v-for="(item,index) in photoData" :key="index.id">
      <img :src="item" alt="" @click="showDot(index)">
      <div class="dot" v-show="flagDot">✓</div>
    </div>
    <!--底部相册选择-->
    <div class="photo-choose">
      <p>相册选择</p>
      <span>(尺寸必须为750*1334)</span>
    </div>
  </div>
</template>

<script>
import img1 from "../assets/cover1.jpg";
import img2 from "../assets/cover2.jpg";
import img3 from "../assets/cover3.jpg";
export default {
  name: "picdata",
  data() {
    return {
      flagDot: false,
      photoData: [img1, img2, img3]
    };
  },
  methods: {
    showDot() {
      this.flagDot = !this.flagDot;
    }
  }
};
</script>

<style scoped>
.container {
  position: absolute;
  width: 100%;
  height: 100%;
}
.cover {
  position: relative;
  width: 100%;
  height: 400px;
  margin-top: 14px;
}
.dot {
  position: absolute;
  right: 14px;
  bottom: 6px;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  text-align: center;
  background: #fe7272;
}
.cover img {
  width: 100%;
  height: 380px;
}
.photo-choose {
  position: absolute;
  bottom: 5px;
  width: 100%;
  height: 48px;
  margin: 0 auto;
  text-align: center;
}
.photo-choose p {
  margin-top: 8px;
  font: 16px PingFangSC;
  color: #f8494c;
}
.photo-choose span {
  font: 12px PingFangSC;
  color: #666666;
}
</style>
