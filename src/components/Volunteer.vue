<template>
  <div class="volunteer">
    <div class="recruit-board flex flex-col align">
      <div class="title slash-title">志愿者招募</div>
      <p style="text-align: center">
        由于小程序现阶段人手较少，为了方便更新小程序、维护社区环境<br/>
        故将志愿者招募信息公布于此板块，希望有志之士能够加入到我们的社区发展中来
      </p>
      <div class="requirement flex">
        <ul class="job-option flex flex-col jcenter">
          <li class="option flex"
              :class="{active: now===i}"
              @click="jump(i)"
              v-for="(ele,i) in jobs">{{ ele.name }}</li>
        </ul>
        <div class="job-detail">
          <p>这里是主要的一个招募条件讯息</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import {ref} from "vue";

const jobs = ref([
  {name: '前端工程师'},
  {name: '后端工程师'},
  {name: '客服'},
  {name: '自媒体运营'},
])

const now = ref(0);

const jump = function (idx) {
  now.value = idx;
}
</script>

<style scoped lang="scss">
.volunteer {
  padding: 40px 60px;
}

.title {
  font-size: 2rem;
  font-weight: bold;
}

.requirement {
  width: 100%;
}

.job-option {
  width: 30%;

  .option {
    position: relative;
    width: 100%;
    padding: 15px 10px;
    margin: 5px 0;
    box-sizing: border-box;
    font-weight: bold;
    font-family: "PingFang SC", '微软雅黑', Helvetica, "Helvetica Neue";
    letter-spacing: 1px;
    transition: all ease-in-out 0.5s;
    cursor: pointer;
  }

  .option:before {
    content: '';
    display: block;
    position: absolute;
    left: 0;
    top: 0;
    width: 3px;
    height: 100%;
    background: #c4453c;
    opacity: 0;
    transition: opacity ease 0.3s;
  }

  .active {
    padding-left: 25px;
    color: #c4453c;
  }

  .active:before {
    opacity: 1;
  }
}
</style>
