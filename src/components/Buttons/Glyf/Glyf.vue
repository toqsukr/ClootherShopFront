<script setup>
    import { ref } from "vue"
    import css from "./Glyf.module.css"

    defineProps(['Key'])

    const isHint = ref(false)
</script>

<template>
    <div @mouseleave="isHint = !isHint" @mouseenter="isHint=!isHint" type="button" :id="css.glyf_container" :key="key">   
        <img :id="css.glyf_img" v-if="Key === 'Каталог'" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/shopping-bag--v1.png" :alt=Key>
        <div :id="css.glyf_hint" v-if="Key === 'Каталог' && isHint">
            <h6>{{ Key }}</h6>
        </div>
        <img :id="css.glyf_img" v-else-if="Key === 'Корзина'" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/shopping-basket.png" :alt=Key>
        <div :id="css.glyf_hint" v-if="Key === 'Корзина' && isHint">
            <h6>{{ Key }}</h6>
        </div>
        <img :id="css.glyf_img" v-else-if="Key === 'Избранное'" src="https://img.icons8.com/windows/200/FFE500/hearts.png" :alt=Key>
        <div :id="css.glyf_hint" v-if="Key === 'Избранное' && isHint">
            <h6>{{ Key }}</h6>
        </div>
        <img :id="css.glyf_img" v-else-if="Key === 'Контакты'" src="https://img.icons8.com/fluency-systems-regular/200/FFE500/telegram-app.png" :alt=Key>
        <div :id="css.glyf_hint" v-if="Key === 'Контакты' && isHint">
            <h6>{{ Key }}</h6>
        </div>
    </div>
</template>