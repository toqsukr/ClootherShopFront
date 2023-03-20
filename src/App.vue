<script setup>
  import Header from './components/Header/Header.vue';
  import SidePanel from './components/SidePanel/SidePanel.vue';
</script>

<template>
  <Header/>
  <SidePanel/>
  <div id="main-container">
  </div>
</template>

<style>
  #main-container {
    height: auto;
    width: auto;
  }
</style>