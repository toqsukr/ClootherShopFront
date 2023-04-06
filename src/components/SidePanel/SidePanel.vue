<script setup>
    import css from "./SidePanel.module.css"
    import Glyf from "../Buttons/Glyf/Glyf.vue"
    defineProps(['isSide']) 

    const glyfs = ["Каталог", "Корзина", "Избранное", "Контакты"]
</script>
<template>
    <div :id="css.side_box">
        <Glyf v-for="glyf in glyfs" :Key=glyf :key=glyf />
    </div>
</template>
