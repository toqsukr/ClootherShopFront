<script setup>
    import css from "./Header.module.css"
    defineProps(['isSide'])
    defineEmits(['changeSide'])

</script>

<template>
    <div :id="css.header_container">
        <div :id="css.menu_group">
            <img @click="$emit('changeSide')" type="button" :class="{[css.menu_img]: true, [css.rotate]: isSide}" src="https://img.icons8.com/ios-glyphs/200/FFE500/menu--v1.png" alt="">
        </div>
        <h1 :id="css.logo_text">Logo</h1>
        <div :id="css.control_btn_group">
        </div>
    </div>
</template>
