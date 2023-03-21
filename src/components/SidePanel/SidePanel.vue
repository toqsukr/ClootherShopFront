<script setup>
    import css from "./SidePanel.module.css"
    import Glyf from "../Buttons/Glyf/Glyf.vue"
    defineProps(['isSide']) 
    const glyfs = ["Профиль", "Корзина", "Избранное", "Контакты"]
</script>
<template>
    <div :class="{[css.side_box]: true, [css.side_box_hidden]: !isSide, [css.side_box_show]: isSide}">
        <Glyf v-for="(glyf, index) in glyfs" :Key=index>{{ glyf }}</Glyf>
    </div>
</template>
