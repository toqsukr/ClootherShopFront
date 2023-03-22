<script setup>
  import { ref } from "vue"
  import Header from './components/Header/Header.vue';
  import SidePanel from './components/SidePanel/SidePanel.vue';
  import ProfileBar from "./components/ProfileBar/ProfileBar.vue";

  const isSide = ref(false)
  const isProfile = ref(false)
  const login = ref(false)
</script>

<template>
  <Header :login="login" :isProfile=isProfile :isSide=isSide  @change-login="() => login=!login" @change-profile="() => isProfile=!isProfile" @change-side="() => isSide=!isSide" />
  <div id="main-container">
    
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