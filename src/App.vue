<script setup>
  import { ref } from "vue"
  import Header from './components/Header/Header.vue';
  import SidePanel from './components/SidePanel/SidePanel.vue';
  import ProfileBar from "./components/ProfileBar/ProfileBar.vue";
  import SignPanel from "./components/SignPanel/SignPanel.vue";

  const isSide = ref(false)
  const isProfile = ref(false)
  const login = ref(false)
  const showWindow = ref(false)

  const hideProfile = () => {
    if(isProfile.value)  isProfile.value = !isProfile.value;
  }
</script>

<template>
  <Header :login=login :isProfile=isProfile :isSide=isSide @change-window="() => showWindow=!showWindow"  @change-login="() => login=!login" @change-profile="() => isProfile=!isProfile" @change-side="() => isSide=!isSide" />
  <div @click="hideProfile" id="main-container">
  </div>
  <SignPanel v-if="!login" :showWindow="showWindow" @change-window="() => showWindow=!showWindow"></SignPanel>
  <ProfileBar :isProfile=isProfile @change-login="() => login=!login" @change-profile="() => isProfile=!isProfile"></ProfileBar>
  <SidePanel :isSide=isSide />
</template>

<style>
  #app {
    position: relative;
    z-index: 1;
    background-color: #F2F2F2;
  }

  #main-container {
    height: auto;
    width: auto;
  }
</style>