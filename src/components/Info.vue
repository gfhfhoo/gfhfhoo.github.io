<template>
  <div class="info flex jcenter">
    <div class="tag flex align flex-col">
      <div class="icon">
        <img src="../assets/weixin_acc.jpg"/>
      </div>
      <div class="detail flex align flex-col">
        <p class="tiny-title">微信公众号</p>
        <span class="tiny-data">诚信点评 | 甄别好坏企业</span>
      </div>
    </div>
    <div class="tag flex align flex-col">
      <div class="icon">
        <img src="../assets/douyin_acc.png"/>
      </div>
      <div class="detail flex align flex-col">
        <p class="tiny-title">官方抖音号</p>
        <span class="tiny-data">诚信点评 | 企业曝光平台</span>
      </div>
    </div>
    <div class="tag flex align flex-col">
      <div class="icon">
        <img src="../assets/icon.jpeg"/>
      </div>
      <div class="detail flex align flex-col">
        <p class="tiny-title">其他入口..</p>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>

</script>

<style scoped lang="scss">
.info {
  width: 100%;
  padding: 40px 0;
}

.tag {
  width: 33%;

  .icon img {
    width: 100px;
    height: 100px;
  }

  .tiny-title {
    font-size: 1.3rem;
    font-weight: bold;
    font-family: "PingFang SC", Helvetica, "Helvetica Neue";
  }

  .tiny-data {
    font-size: 1.1rem;
    color: rgb(26, 26, 26);
    font-family: "PingFang SC", Helvetica, "Helvetica Neue";
  }
}

</style>
