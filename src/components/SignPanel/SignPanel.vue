<script setup>
    import css from "./SignPanel.module.css"

    defineProps(['showWindow'])
    const emit = defineEmits(['changeWindow'])

</script>

<template>
    <div @click="$emit('changeWindow')" :class="{[css.sign_main_container]: true, [css.window_container_appearance]: showWindow}">
        <div @click="$emit('changeWindow')" :class="{[css.sign_window_container]: true, [css.window_appearance]: showWindow}">
            <div :id="css.window_header" >
                <img @click="$emit('changeWindow')" type="button" :id="css.sign_close_img" src="https://img.icons8.com/material/200/FFE500/multiply--v1.png" alt="">
            </div>
        </div>
    </div>
</template>