<template>
  <div class="slide-container" @mouseover="showSidebar(true)" @mouseleave="showSidebar(false)">
    <div class="carousel" :style="{width: `${contents.length*100}%`}" ref="carousel">
      <div :seq="i" class="carousel-slide" :style="{width: `${100/contents.length}%`}" v-for="(ele,i) in contents">
        <img class="slide-img" :src="ele">
      </div>
    </div>
    <div class="tooltip">
      <ul class="switcher flex align">
        <li :class="{active: i===(now+1)%contents.length}" @click="jump(i)" v-for="(ele,i) in contents"></li>
      </ul>
    </div>
    <div class="sidebar">
      <div class="prev" :class="{prevHide: !isShowSidebar}" @click="prev"></div>
      <div class="next" :class="{nextHide: !isShowSidebar}" @click="next"></div>
    </div>
  </div>
</template>

<script lang="ts" setup>

import {onMounted, ref} from "vue";

const contents = ref([
  "/slide/s1.png",
  "/slide/s2.png",
  "/slide/s3.jpeg",
  "/slide/s4.png",
]);

const now = ref(0);
const counter = ref(null);
const isShowSidebar = ref(false);

const carousel = ref<HTMLElement | null>(null);

onMounted(() => {
  const el = carousel.value;
  const len = contents.value.length;

  for (let i = 1; i <= len - 1; ++i) shift(el);

  if (len > 2) el.style.transform = `translateX(-${100 / len}%)`;
  else el.style.transform = `translateX(0%)`;

  counter.value = setInterval(() => doSlide(), 2000);

})

const showSidebar = function (b) {
  isShowSidebar.value = b;
}

const resetCounter = function () {
  clearInterval(counter.value);
  counter.value = setInterval(() => doSlide(), 2000);
}

const doSlide = function () {
  postSlide(shift);
  readySlide();
}

const readySlide = function (reserve?: boolean) {
  const el = carousel.value;
  const len = contents.value.length;
  if (!reserve) {
    if (len > 2) el.style.transform = `translateX(-${2 * 100 / len}%)`;
    else el.style.transform = `translateX(-50%)`;
  } else {
    el.style.transform = 'translateX(0%)';
  }
  el.style.transition = `transform 300ms ease 0s`;
}

const postSlide = function (poster: any) {
  const el = carousel.value;
  const len = contents.value.length;
  el.addEventListener('transitionend', () => {
    el.style.transition = `transform 0s ease 0s`;
    if (len > 2) el.style.transform = `translateX(-${100 / len}%)`;
    else el.style.transform = `translateX(0%)`;
    poster(el);
  }, {once: true})
}

const next = function () {
  resetCounter();
  postSlide(shift);
  readySlide();
}

const prev = function () {
  resetCounter();
  postSlide(unshift);
  readySlide(true);
}

const shift = function (el: HTMLElement) {
  let top = el.children[0];
  el.removeChild(el.firstChild);
  el.appendChild(top);
  now.value = (now.value + 1) % contents.value.length;
}

const unshift = function (el: HTMLElement) {
  let bottom = el.children[el.children.length - 1];
  el.removeChild(el.lastChild);
  el.insertBefore(bottom, el.children[0]);
  now.value = (now.value - 1 + contents.value.length) % contents.value.length;
}

const jump = function (to: number) {
  resetCounter();
  const el = carousel.value;
  let t = to + contents.value.length - now.value - 1;
  for (let i = 1; i <= t; ++i) shift(el);
}

</script>

<style scoped lang="scss">
.slide-container {
  position: relative;
  width: 100%;
  height: 500px;
  overflow-x: hidden;
}

.carousel {
  height: 100%;
  overflow: hidden;
  background: black;
}

.carousel-slide {
  display: inline-block;
}

.slide-img {
  width: 100%;
  height: 100%;
  background-size: cover;
}

.tooltip {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  z-index: 99;

  .switcher {
    height: 20px;
  }

  .switcher li {
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    margin: 0 5px;
    cursor: pointer;
    background: rgba(255, 255, 255, 0.8);
  }

  .switcher .active {
    width: 15px;
    height: 15px;
    background: rgba(255, 255, 255);
  }
}

.prevHide {
  transform: translate(-100%, -50%) !important;
}

.nextHide {
  transform: translate(100%, -50%) !important;
}

.sidebar {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow-x: hidden;

  .prev {
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 50px;
    height: 20%;
    background: rgba(128, 128, 128, 0.6);
    cursor: pointer;
    transition: all ease .5s;
  }

  .next {
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 50px;
    height: 20%;
    background: rgba(128, 128, 128, 0.6);
    cursor: pointer;
    transition: all ease .5s;
  }

  .prev::before {
    content: '\e5e0';
    position: relative;
    display: block;
    font-family: 'Google Fonts';
    scale: 2;
    color: rgb(255, 255, 255);
  }

  .next::before {
    content: '\e5e1';
    position: relative;
    display: block;
    font-family: 'Google Fonts';
    scale: 2;
    color: rgb(255, 255, 255);
  }
}
</style>