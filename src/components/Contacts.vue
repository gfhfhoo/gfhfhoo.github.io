<template>
  <div class="contact-kf flex flex-col align">
    <div class="title slash-title">如何成为志愿者</div>
    <div class="container">
      <img class="example" src="/info.jpeg"/>
      <div class="steps">
        <StepLine @click="jump(1)" :class="{active: nowStep===1}" step="1">
          <p>这是一个示例</p>
        </StepLine>
        <StepLine @click="jump(2)" :class="{active: nowStep===2}" step="2">
          <p>这是一个示例2</p>
        </StepLine>
        <StepLine @click="jump(3)" :class="{active: nowStep===3}" step="3">
          <p>这是一个示例3</p>
        </StepLine>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import StepLine from '../components/tiny/StepLine.vue'
import {ref} from "vue";

const nowStep = ref(1);

const jump = function (step) {
  nowStep.value = step
}
</script>

<style scoped lang="scss">
.title {
  font-size: 2rem;
  font-weight: bold;
}

.contact-kf {
  padding: 40px 60px;
}

.container {
  display: flex;
  width: 100%;
  margin-top: 10px;
}

.example {
  width: 270px;
  height: 577px;
}

.steps {
  flex: 1;
  padding: 0 20px;
  box-sizing: border-box;
}
</style>
