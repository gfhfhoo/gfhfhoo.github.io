<template>
  <div class="box">
    <slot />
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped lang="scss">
.box {
  width: 1220px;
  min-width: 1220px;
  margin-top: 50px;
  box-sizing: border-box;
  border: 1px solid rgba(0, 0, 0, .14);
  box-shadow: 0 3px 8px -6px rgba(0, 0, 0, .14);
  border-radius: 8px;
  background-color: #fff;
}

</style>
