<script setup>
    import { ref } from 'vue'
    import css from './Glyf.module.css'

    defineProps(['Key', 'key'])

    const isHint = ref(false)
</script>

<template>
    <div
        @mouseleave="isHint = !isHint"
        @mouseenter="isHint = !isHint"
        type="button"
        :id="css.glyf_container"
        :key="key">
        <div
            :class="{ [css.bottom_right_border_round]: Key === 'Контакты' }"
            :id="css.glyf_img_container">
            <img
                :key="key"
                :class="{
                    [css.glyf_img]: true,
                    [css.glyf_img_shopping_bag]: true,
                }"
                v-if="Key === 'Каталог'"
                :alt="Key" />
            <img
                :class="{
                    [css.glyf_img]: true,
                    [css.glyf_img_shopping_basket]: true,
                }"
                v-else-if="Key === 'Корзина'"
                :alt="Key" />
            <img
                :class="{
                    [css.glyf_img]: true,
                    [css.glyf_img_favorite]: true,
                }"
                v-else-if="Key === 'Избранное'"
                :alt="Key" />
            <img
                :class="{
                    [css.glyf_img]: true,
                    [css.glyf_img_contacts]: true,
                }"
                v-else-if="Key === 'Контакты'"
                :alt="Key" />
        </div>
        <div
            :class="{
                [css.slider_hint]: true,
                [css.slider_show]: isHint,
                [css.top_right_border_round]: Key != 'Каталог',
            }">
            <h6 :id="css.glyf_text">{{ Key }}</h6>
        </div>
    </div>
</template>
