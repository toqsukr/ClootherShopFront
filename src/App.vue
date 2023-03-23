<script setup>
  import { ref } from "vue"
  import Header from './components/Header/Header.vue';
  import SidePanel from './components/SidePanel/SidePanel.vue';
  import ProfileBar from "./components/ProfileBar/ProfileBar.vue";

  const isSide = ref(false)
  const isProfile = ref(false)
  const login = ref(false)

  const hideProfile = () => {
    if(isProfile.value)  isProfile.value = !isProfile.value;
  }
</script>

<template>
  <Header :login="login" :isProfile=isProfile :isSide=isSide  @change-login="() => login=!login" @change-profile="() => isProfile=!isProfile" @change-side="() => isSide=!isSide" />
  <div @click="hideProfile" id="main-container">
      <h1 v-for="i in 30">:DDD</h1>
  </div>
  <ProfileBar :isProfile=isProfile @change-login="() => login=!login" @change-profile="() => isProfile=!isProfile"></ProfileBar>
  <SidePanel :isSide=isSide />
</template>

<style>
  #app {
    position: relative;
    background-color: #F2F2F2;
  }

  #main-container {
    height: auto;
    width: auto;
  }
</style>