<script setup>
    import css from "./Header.module.css"
    defineProps(['isSide', 'isProfile', 'login'])
    const emit = defineEmits(['changeSide', 'changeProfile', 'changeLogin', 'changeWindow'])

    const handleProfile = () => {
        emit('changeProfile')
    }

    const handleSign = () => {
        emit('changeWindow')
    }

    
  function handleLogin() {
        emit('changeProfile');
        emit('changeLogin')
    }
</script>

<template>
    <div :id="css.header_container">
        <div :id="css.menu_group">
            <img @click="$emit('changeSide')" type="button" :class="{[css.menu_img]: true, [css.rotate]: isSide}" src="https://img.icons8.com/ios-glyphs/200/FFE500/menu--v1.png" alt="">
        </div>
        <h1 @click="!login && (isProfile ? handleLogin() : $emit('changeLogin'))" :id="css.logo_text">Shop</h1>
        <div :id="css.profile_container">
            <div type="button" :id="css.profile_icon_container">
                <img @click=handleProfile v-if="login" :id="css.profile_icon" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/user.png" alt="profile" />
                <img @click=handleSign v-else src="https://img.icons8.com/material/200/FFE500/enter-2--v1.png" :id="css.profile_icon" alt="sign-in">
                <img @click=handleProfile v-if="login" :class="{[css.profile_down]:true, [css.profile_down_show]: isProfile}" src="https://img.icons8.com/material/200/FFFFFF/sort-down--v1.png" alt="">
            </div>
        </div>
    </div>
</template>
