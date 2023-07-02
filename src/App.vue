<template>
  <div class="root">
    <div class="nav">
      <div class="nav-bg" :class="{'nav-bg-blur': scrolled}"></div>
      <div class="nav-content">
        <h1 class="title">诚信点评</h1>
        <div class="links">
          <router-link class="nav_link"
                       active-class="link_active"
                       exact-active-class="link_active"
                       to="/">首页
          </router-link>
        </div>
        <div class="quick_entry flex align" :class="{'quick_show': scrolled450}">
          <img id="tiny_icon" src="./assets/weixin_app.png"/>
          <img id="tiny_icon" src="./assets/douyin_app.png"/>
        </div>
      </div>
    </div>
    <router-view></router-view>
    <Footer/>
  </div>
</template>

<script setup lang="ts">
import Footer from "./components/Footer.vue";
import {onMounted, ref} from "vue";

const scrolled = ref(false);
const scrolled450 = ref(false);

onMounted(() => {
  window.addEventListener('scroll', () => {
    let sc = window.scrollY || document.body.scrollTop
    scrolled.value = sc > 125;
    scrolled450.value = sc > 450;
  }, true)
})
</script>

<style scoped lang="scss">
.nav {
  display: flex;
  align-items: center;
  position: fixed;
  height: 100px;
  width: 100%;
  top: 0;
  color: #fff;
  z-index: 99;

  .nav-bg {
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: var(--nav-bg-color);
    transition: all 0.5s cubic-bezier(0.28, 0.11, 0.32, 1);
  }

  .nav-bg-blur {
    background-color: var(--nav-bg-color-offset);
    background-attachment: scroll;
    backdrop-filter: saturate(180%) blur(20px);
  }

  .nav-content {
    position: absolute;
    display: flex;
    align-items: center;
    width: 100%;
    padding: 0 20px;
    box-sizing: border-box;

    .title {
      width: 100px;
      font-size: 1.5rem;
    }
  }

  .quick_entry {
    flex: 1;
    display: flex;
    justify-content: flex-end;
    opacity: 0;
    transition: opacity .5s linear;
  }

  .quick_show {
    opacity: 1;
  }

  .links {
    width: 60%;
    margin-left: 120px;
  }

  .nav_link {
    font-size: 16px;
    color: grey;
    text-decoration: none;
    margin-right: 40px;
  }

  .link_active {
    color: #fff;
  }

  #tiny_icon {
    align-self: flex-end;
    width: 70px;
    height: 70px;
  }

  #tiny_icon:first-child {
    margin-right: 10px;
  }
}
</style>
