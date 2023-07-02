<template>
  <div class="team">
    <div class="backdrop flex jcenter align">
      <p class="backdrop-title">主要成员</p>
    </div>
    <div class="nine-sq">
      <div class="wrapper">
        <img :src="icons[Math.floor(Math.random()*3)]" v-for="(ele,i) in icons"/>
      </div>
      <div class="wrapper">
        <img :src="icons[Math.floor(Math.random()*3)]" v-for="(ele,i) in icons"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>

import {ref} from "vue";

const icons = ref([
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
  '/icons/i1.webp',
  '/icons/i2.webp',
  '/icons/i3.png',
])
</script>

<style scoped lang="scss">
.team {
  position: relative;
  min-height: 110px;
  max-height: 440px;
  background: rgb(32, 32, 32);
  overflow: hidden;
}

.backdrop {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100px;
  background: linear-gradient(rgba(17, 17, 17, 0.9), rgba(17, 17, 17, 0.2));
  z-index: 89;
}

.backdrop-title {
  font-size: 2rem;
  color: #ffffff;
}

.nine-sq {
  display: flex;
  width: 200%;
  height: 100%;
  overflow: hidden;
}

.wrapper {
  display: inline-block;
  width: 50%;
  height: 100%;
  scale: 1.1;
  text-align: center;
  overflow: hidden;
}

.wrapper > img {
  width: 110px;
  height: 110px;
  float: left;
}

.wrapper:not(:first-child) {
  transform: translateX(-8px);
}
</style>