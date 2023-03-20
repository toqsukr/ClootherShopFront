<script setup>
    import {ref} from "vue"
    import css from "./Header.module.css"

    const isSide = ref(false)

</script>

<template>
    <div :id="css.header_container">
        <div :id="css.menu_group">
            <img @click="isSide=!isSide" type="button" :class="{[css.menu_img]: true, [css.rotate]: !isSide}" src="https://img.icons8.com/ios-glyphs/200/FFE500/menu--v1.png" alt="">
        </div>
        <h1 :id="css.logo_text">Logo</h1>
        <div :id="css.control_btn_group">
            <button :id="css.circle_btn" style="background-color: #1FFF43;"></button>
            <button :id="css.circle_btn" style="background-color: #FBFF3E;"></button>
            <button :id="css.circle_btn" style="background-color: #FF3030;"></button>
        </div>
    </div>
</template>
