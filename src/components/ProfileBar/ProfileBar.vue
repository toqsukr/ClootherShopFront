<script setup>
    import css from "./ProfileBar.module.css"

    defineProps(['isProfile'])
    const emit = defineEmits(['changeLogin', 'changeProfile'])
    const profileItems = ['Ilya.pakylov@gmail.com', 'Управление аккаунтом', 'Выйти']

    const handleLogout = (index) => {
        if(index === profileItems.length - 1) {
            emit('changeLogin')
            emit('changeProfile')
        } 
    }

</script>

<template>
    <div :id="css.profile_main_container">
        <div :class="{[css.profile_bar_container]: true, [css.profile_bar_container_show]: isProfile}">
            <h6 @click=handleLogout(index) :type="index == 0 ? 'span' : 'button'" :class="{[css.border_round]: index === profileItems.length - 1}" :id="css.profile_item" v-for="(item, index) in profileItems" :key="index">{{ item }}</h6>
        </div>
    </div>
</template>
