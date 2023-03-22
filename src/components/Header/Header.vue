<script setup>
    import { ref } from "vue"
    import css from "./Header.module.css"
    defineProps(['isSide'])
    defineEmits(['changeSide'])

    const login = ref(false)
</script>

<template>
    <div :id="css.header_container">
        <div :id="css.menu_group">
            <img @click="$emit('changeSide')" type="button" :class="{[css.menu_img]: true, [css.rotate]: isSide}" src="https://img.icons8.com/ios-glyphs/200/FFE500/menu--v1.png" alt="">
        </div>
        <h1 :id="css.logo_text">Logo</h1>
        <div :id="css.profile_container">
            <div @click="login=!login" type="button" :id="css.profile_icon_container">
                <img v-if="login" :id="css.profile_icon" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/user.png" alt="profile" />
                <img v-if="login" :id="css.profile_down" src="https://img.icons8.com/material/200/FFFFFF/sort-down--v1.png" alt="">
                <img v-else src="https://img.icons8.com/material/200/FFE500/enter-2--v1.png" :id="css.profile_icon" alt="sign-in">
            </div>
        </div>
    </div>
</template>
