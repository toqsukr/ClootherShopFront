<script setup>
    import css from "./Glyf.module.css"

    defineProps(["Key"])
</script>

<template>
    <div type="button" :id="css.glyf_container" :key="key">   
        <img :id="css.glyf_img" v-if="Key === 0" src="https://img.icons8.com/material-rounded/200/FFE500/user.png" alt="">
        <img :id="css.glyf_img" v-else-if="Key === 1" src="https://img.icons8.com/pastel-glyph/200/FFE500/shopping-cart--v2.png" alt="">
        <img :id="css.glyf_img" v-else-if="Key === 2" src="https://img.icons8.com/windows/200/FFE500/hearts.png" alt="">
        <img :id="css.glyf_img" v-else-if="Key === 3" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/telegram-app.png" alt="">
        <button :id="css.glyf_text"><slot></slot></button>
    </div>
</template>