<script setup>
    import css from "./SignPanel.module.css"

    defineProps(['showWindow', 'login'])
    const emit = defineEmits(['changeWindow'])

</script>

<template>
    <div :id="css.sign_main_container">
        <div :id="css.sign_window_container">
            <div :id="css.window_header" >
                <img @click="$emit('changeWindow')" type="button" :id="css.sign_close_img" src="https://img.icons8.com/material/200/FFE500/multiply--v1.png" alt="">
            </div>
            <div :id="css.window_title">Вход</div>
            <div :id="css.window_form">
                <div :id="login_container">
                    <p :id="css.form_text">Логин</p>
                    <input :id="css.sign_input" type="email">
                </div>
                <div :id="password_container">
                    <p :id="css.form_text">Пароль</p>
                    <input :id="css.sign_input" type="password" >
                </div>
            </div>
            <div :id="css.button_container">
                <a :id="css.form_button" type="button">Войти</a>
            </div>
            <div :id="css.change_form" type="button">Впервые у нас? Зарегистрируйтесь!</div>
        </div>
    </div>
</template>