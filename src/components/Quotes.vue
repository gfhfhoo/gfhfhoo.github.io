<template>
  <div class="quotes flex jcenter">
    <div class="container">

    </div>
  </div>
</template>

<script lang="ts" setup>

</script>

<style scoped lang="scss">
.quotes {
  width: 100%;
  padding: 80px 0;

}

.container {
  position: relative;
  width: 80%;
  height: 400px;
}

.container::before {
  content: '\201c';
  display: block;
  position: absolute;
  color: orange;
  font-size: 8em;
  transform: translateX(-60px) translateY(-80px);
  font-family: "PingFang SC";
}

.container::after {
  content: '\201d';
  display: block;
  position: absolute;
  bottom: 0;
  right: 0;
  color: orange;
  font-size: 8em;
  transform: translateX(60px) translateY(160px);
  font-family: "PingFang SC";
}

</style>
