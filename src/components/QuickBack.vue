<template>
  <div class="back_top flex align jcenter"
       :class="{show: scrolled450}"
       @click="backToTop"
  >
  </div>
</template>

<script lang="ts" setup>
import {onMounted, ref} from "vue";

const scrolled450 = ref(false);

onMounted(() => {
  window.addEventListener('scroll', () => {
    let sc = window.scrollY || document.body.scrollTop
    scrolled450.value = sc > 450;
  }, true)
})

const backToTop = function () {
  window.scrollTo({top: 0, behavior: 'smooth'})
}
</script>

<style scoped lang="scss">
.back_top {
  position: fixed;
  width: 50px;
  height: 50px;
  bottom: 20px;
  right: 20px;
  transform: translateX(200%);
  background: var(--backtop-bg-color);
  border-radius: 3px;
  color: white;
  z-index: 999;
  transition: all ease 0.4s;
}

.back_top:after {
  content: '\e5ce';
  width: 100%;
  height: 100%;
  font-family: 'Google Fonts';
  font-size: 3rem;
  text-align: center;
  cursor: pointer;
}

.back_top:hover {
  color: orange !important;
}

.show {
  transform: translateX(0);
}

</style>
