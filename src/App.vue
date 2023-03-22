<script setup>
  import { ref } from "vue"
  import Header from './components/Header/Header.vue';
  import SidePanel from './components/SidePanel/SidePanel.vue';

  const isSide = ref(false)
</script>

<template>
  <Header :isSide=isSide @change-side="() => isSide=!isSide" />
    <div id="main-container">

    </div>
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