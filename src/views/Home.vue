<template>
  <div class="main_page">
    <Header/>
    <HomeBox>
      <Info/>
    </HomeBox>
    <HomeBox>
      <Volunteer/>
    </HomeBox>
    <HomeBox>
      <Contacts/>
    </HomeBox>
    <HomeBox>
      <Team/>
    </HomeBox>
    <QuickBack/>
  </div>
</template>

<script setup lang="ts">
import Header from "../components/Header.vue";
import HomeBox from "../components/HomeBox.vue";
import Info from "../components/Info.vue";
import QuickBack from "../components/QuickBack.vue";
import Volunteer from "../components/Volunteer.vue";
import Contacts from "../components/Contacts.vue";
import Team from "../components/Team.vue";

</script>

<style scoped lang="scss">

.main_page {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 40px;
  padding-top: 60px;
}

</style>
