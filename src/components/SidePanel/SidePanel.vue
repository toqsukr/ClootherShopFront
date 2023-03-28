<script setup>
    import css from "./SidePanel.module.css"
    import Glyf from "../Buttons/Glyf/Glyf.vue"
    defineProps(['isSide']) 

    const glyfs = ["Каталог", "Корзина", "Избранное", "Контакты"]
</script>
<template>
    <transition name="side_box">
        <div :class="{[css.side_box]: true, [css.side_box_hidden]: !isSide, [css.side_box_show]: isSide}">
            <Glyf v-for="glyf in glyfs" :Key=glyf :key=glyf />
        </div>
    </transition>
</template>
