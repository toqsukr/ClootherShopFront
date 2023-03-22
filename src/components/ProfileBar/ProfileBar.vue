<script setup>
    import css from "./ProfileBar.module.css"

    defineProps(['isProfile'])
</script>

<template>
    <div :class="{[css.profile_bar_container]: true, [css.profile_bar_container_show]: isProfile}">

    </div>
</template>
