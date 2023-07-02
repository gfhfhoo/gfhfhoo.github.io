<template>
  <div class="header_wrapper">
<!--    <video class="backdrop" autoplay muted loop playsinline>-->
<!--      <source src="../assets/example.mp4" type="video/mp4">-->
<!--    </video>-->
<!--    <div class="video-mask"></div>-->
    <div class="header flex align flex-col">
      <h1 class="main_title">诚信点评 | 企业曝光平台</h1>
      <div class="flex fade-up" style="width: 100%;flex:1;">
        <div class="left flex align jcenter">
          <div class="banner">
            <h1>勇揭职场真相</h1>
            <h1 class="offset">为打工人而战</h1>
          </div>
          <div class="entry flex align">
            <div class="entry_header flex align">
              <img id="small_icon" src="../assets/icon.jpeg"/>
              <span class="small_title">打工人诚信点评小程序</span>
            </div>
            <div class="qr_code">
              <img id="qr_code_img" class="mr20" src="../assets/weixin_app.png"/>
              <img id="qr_code_img" src="../assets/douyin_app.png"/>
            </div>
          </div>
        </div>
        <div class="right">
          <MainSlide/>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import MainSlide from "./slide/MainSlide.vue";
</script>

<style scoped lang="scss">
.header_wrapper {
  position: relative;
  width: 100%;
  height: calc(100vh - 100px);
  background-color: rgb(48, 49, 52);
  overflow: hidden;
}

.backdrop {
  position: absolute;
  width: 100%;
  height: 120%;
  object-fit: fill;
  transform: translateY(-110px);
}

.video-mask {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.45);
  z-index: 2;
}

.header {
  position: relative;
  width: 100%;
  height: 100%;
  padding: 0 50px 60px 50px;
  box-sizing: border-box;
  z-index: 9;


  .main_title {
    margin-top: 40px;
    margin-bottom: 40px;
    color: #fff;
    font-size: 3rem;
  }

  .fade-up {
    position: relative;
    animation: slide_up ease-in-out .8s;
    z-index: 1;
  }
}

#small_icon {
  width: 50px;
  height: 50px;
  border-radius: 50%;
}

#qr_code_img {
  width: 120px;
  height: 120px;
}

.left {
  width: 40%;
  flex-direction: column;
}

.right {
  width: 60%;
}

.banner {
  color: #fff;
  letter-spacing: .3rem;
  margin-bottom: 50px;
}

.entry {
  flex-direction: column;

  .entry_header {
    padding-bottom: 20px;
  }

  .small_title {
    font-size: 1.1rem;
    margin-left: 10px;
    color: #fff;
  }
}

.offset:before {
  content: '';
  display: inline-block;
  width: 63px;
}

</style>
