<template>
  <div class="step-wrapper">
    <div class="step flex align jcenter" @click="emits('click')">
      <div class="wrapper flex align jcenter">
        <div class="round flex align jcenter">
          <span>{{ props.step }}</span>
        </div>
      </div>
    </div>
    <div class="content">
      <slot/>
    </div>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps(['step'])

const emits = defineEmits(['click'])

</script>

<style scoped lang="scss">
.step {
  position: relative;
  width: 100%;
  height: 40px;
  margin: 20px 0;
  box-sizing: content-box;
  cursor: pointer;
}

.step:before {
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
  width: 60px;
  height: fit-content;
  background: #ffffff;
  z-index: 80;
}

.round {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  border: 2px solid #111;
  background: #ffffff;
  font-size: 1.5rem;
}

.content {
  padding-left: 40px;
  box-sizing: border-box;
}

.active .step {
  color: #c4453c;
}

.active .round {
  border: 2px solid #c4453c;
}

.active .step:before {
  border: .5px solid rgba(196, 69, 60, 0.4);
}

.step, .round, .step:before {
  transition: all ease .3s;
}
</style>