<script setup>
    import css from './Header.module.css'
    defineProps(['isSide', 'isProfile', 'login', 'showWindow'])
    const emit = defineEmits([
        'changeSide',
        'changeProfile',
        'changeLogin',
        'changeWindow',
        'changeSide',
    ])

    const handleSide = (showWindow) => {
        if (!showWindow) emit('changeSide')
    }

    const handleProfile = () => {
        emit('changeProfile')
    }

    const handleSign = (isSide) => {
        emit('changeWindow')
        if (isSide) emit('changeSide')
    }

    function handleLogin() {
        emit('changeProfile')
        emit('changeLogin')
    }
</script>

<template>
    <div :id="css.header_container">
        <div :id="css.menu_group">
            <span
                @click="handleSide(showWindow)"
                type="button"
                :class="{ [css.menu_img]: true, [css.rotate]: isSide }"
                alt="" />
        </div>
        <h1
            @click="
                !login && (isProfile ? handleLogin() : $emit('changeLogin'))
            "
            :id="css.logo_text">
            Shop
        </h1>
        <div :id="css.profile_container">
            <div type="button" :id="css.profile_icon_container">
                <span
                    @click="handleProfile"
                    v-if="login"
                    :id="css.profile_icon"
                    alt="profile" />
                <span
                    @click="handleSign(isSide)"
                    v-else
                    :id="css.sign_in_icon"
                    alt="sign-in" />
                <span
                    @click="handleProfile"
                    v-if="login"
                    :class="{
                        [css.profile_down]: true,
                        [css.profile_down_show]: isProfile,
                    }"
                    alt="" />
            </div>
        </div>
    </div>
</template>
