<template>
  <div class="job flex align jcenter">
    <div class="wrapper flex align jcenter">
      <span>{{ props.name }}</span>
    </div>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps(['name'])
</script>

<style scoped lang="scss">
.job {
  position: relative;
  width: 100%;
  height: 40px;
  margin: 20px 0;
  box-sizing: content-box;
}

.job:before {
  content: '';
  position: absolute;
  width: 100%;
  top: 50%;
  transform: translateY(-50%);
  border: .5px solid rgba(128, 128, 128, 0.4);
  z-index: 0;
}

.wrapper {
  position: relative;
  height: fit-content;
  background: #ffffff;
  z-index: 99;
}
</style>