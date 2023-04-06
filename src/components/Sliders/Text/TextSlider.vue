<script setup>
    import css from "./TextSlider.module.css"
    defineProps(['Key', 'key'])
</script>

<template>
    <div :id="css.slider_container">
        <div :class="{[css.slider]: true, [css.top_right_border_round]: Key != 'Каталог'}">
            <h6 :id="css.glyf_text" >{{ Key }}</h6>
        </div>
    </div>
</template>