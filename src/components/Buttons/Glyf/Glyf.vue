<script setup>
    import { ref } from "vue"
    import css from "./Glyf.module.css"
    import TextSlider from '../../Sliders/Text/TextSlider.vue'

    defineProps(['Key', 'key'])

    const isHint = ref(false)
</script>
 
<template>
    <div @touchstart="isHint = !isHint" @mouseleave="isHint = !isHint" @mouseenter="isHint=!isHint" type="button" :id="css.glyf_container" :key="key">   
        <div :class="{[css.bottom_right_border_round]: Key === 'Контакты'}" :id="css.glyf_img_container" >
            <img :key="key" :id="css.glyf_img" v-if="Key === 'Каталог'" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/shopping-bag--v1.png" :alt=Key>
            <img :id="css.glyf_img" v-else-if="Key === 'Корзина'" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/shopping-basket.png" :alt=Key>
            <img :id="css.glyf_img" v-else-if="Key === 'Избранное'" src="https://img.icons8.com/windows/200/FFE500/hearts.png" :alt=Key>
            <img :id="css.glyf_img" v-else-if="Key === 'Контакты'" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/telegram-app.png" :alt=Key>
        </div>
        <Transition name="glyf-text-slide">
            <TextSlider :Key="Key" v-if="isHint"/>
        </Transition>
    </div>
</template>

<style>

    .glyf-slide-enter-active,
    .glyf-slide-leave-active {
        transition: transform 0.4s;
    }

    .glyf-slide-enter-to,
    .glyf-slide-leave-from {
        transform: translateX(80px);
    }
</style>