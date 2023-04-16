<script setup>
    import { ref } from 'vue'
    import { Transition } from 'vue'
    import Header from './components/Header/Header.vue'
    import SidePanel from './components/SidePanel/SidePanel.vue'
    import ProfileBar from './components/ProfileBar/ProfileBar.vue'
    import SignPanel from './components/SignPanel/SignPanel.vue'

    const isSide = ref(false)
    const isProfile = ref(false)
    const login = ref(false)
    const showWindow = ref(false)

    const hideProfile = () => {
        if (isProfile.value) isProfile.value = !isProfile.value
    }
</script>

<template>
    <Header
        :login="login"
        :isProfile="isProfile"
        :isSide="isSide"
        :showWindow="showWindow"
        @change-window="() => (showWindow = !showWindow)"
        @change-login="() => (login = !login)"
        @change-profile="() => (isProfile = !isProfile)"
        @change-side="() => (isSide = !isSide)" />
    <div @click="hideProfile" id="main-container"></div>
    <Transition name="sign-background-appearance">
        <div
            @click="showWindow = !showWindow"
            v-if="!login && showWindow"
            id="sign-background"></div>
    </Transition>
    <Transition name="sign-appearance">
        <SignPanel
            v-if="!login && showWindow"
            :login="login"
            :showWindow="showWindow"
            @change-window="() => (showWindow = !showWindow)"></SignPanel>
    </Transition>
    <Transition name="profile-slide">
        <ProfileBar
            v-if="isProfile"
            :isProfile="isProfile"
            @change-login="() => (login = !login)"
            @change-profile="() => (isProfile = !isProfile)"></ProfileBar>
    </Transition>
    <Transition name="sidepanel-slide">
        <SidePanel v-if="isSide" :isSide="isSide" />
    </Transition>
</template>

<style>
    #app {
        position: relative;
        z-index: 1;
        background-color: #f2f2f2;
    }

    #main-container {
        height: auto;
        width: auto;
    }

    #sign-background {
        width: 100%;
        height: 100%;
        background-color: #25252575;
        display: flex;
        position: fixed;
        top: 0;
    }

    .sign-background-appearance-enter-from,
    .sign-background-appearance-leave-to {
        opacity: 0;
    }

    .sign-background-appearance-enter-active,
    .sign-background-appearance-leave-active {
        transition: opacity 0.5s;
    }

    .sign-background-appearance-enter-to,
    .sign-background-appearance-leave-from {
        opacity: 1;
    }

    .sign-appearance-enter-from,
    .sign-appearance-leave-to {
        opacity: 0;
        transform: scale(0);
    }

    .sign-appearance-enter-active,
    .sign-appearance-leave-active {
        transition: all 0.5s;
    }

    .sign-appearance-enter-to,
    .sign-appearance-leave-from {
        transform: scale(1);
        opacity: 1;
    }

    .sidepanel-slide-enter-from,
    .sidepanel-slide-leave-to {
        transform: translateX(-66px);
    }

    .sidepanel-slide-enter-active,
    .sidepanel-slide-leave-active {
        transition: transform 0.4s;
    }

    .profile-slide-enter-from,
    .profile-slide-leave-to {
        transform: translateY(-210px);
    }

    .profile-slide-enter-active,
    .profile-slide-leave-active {
        transition: transform 0.4s;
    }
</style>
