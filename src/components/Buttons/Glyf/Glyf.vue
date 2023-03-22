<script setup>
    import { ref } from "vue"
    import css from "./Glyf.module.css"

    defineProps(['Key'])

    const isHint = ref(false)
</script>

<template>
    <div @mouseleave="isHint = !isHint" @mouseenter="isHint=!isHint" type="button" :id="css.glyf_container" :key="key">   
        <img :id="css.glyf_img" v-if="Key === 'Каталог'" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/shopping-bag--v1.png" :alt=Key>
        <img :id="css.glyf_img" v-else-if="Key === 'Корзина'" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/shopping-basket.png" :alt=Key>
        <img :id="css.glyf_img" v-else-if="Key === 'Контакты'" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/telegram-app.png" :alt=Key>
        <img :id="css.glyf_img" v-else-if="Key === 'Избранное'" src="https://img.icons8.com/windows/200/FFE500/hearts.png" :alt=Key>
        <div :class="{[css.glyf_hint]:true, [css.glyf_hint_show]: isHint}">
            <h6 :id="css.glyf_text" >{{ Key }}</h6>
        </div>
    </div>
</template>