<template>
  <div class="footer flex align flex-col">
    <div class="content flex align flex-col">
      <div class="site">
        <div class="copyright">
          Copyright © Everything Inc.
        </div>
        <div class="record">
          互联网备案号：京ICP备11111111号-1
        </div>
      </div>
    </div>
  </div>
</template>

<script>
</script>

<style scoped lang="scss">
.footer {
  width: 100%;
  margin-top: 120px;
  padding: 20px 50px 60px 50px;
  background-color: rgb(250, 250, 250);
  box-sizing: border-box;

  .content {
    width: 80%;
    font-size: .8rem;
    color: gray;
  }

  .site {
    display: flex;
    flex-direction: column;
    align-items: center;
    line-height: 1.3rem;
  }
}
</style>
