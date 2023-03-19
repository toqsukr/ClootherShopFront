<script setup>
    import {ref} from "vue"

    const isSide = ref(false)

    const handleMenu = () => {
        isSide.value
        ?
            document.getElementById("menu-img").style.setProperty("transform", "rotate(0deg)")
        :
            document.getElementById("menu-img").style.setProperty("transform", "rotate(-90deg)")
        isSide.value = !isSide.value
    }
</script>

<template>
    <div id="header-container">
        <div id="menu-group">
            <img @click=handleMenu type="button" id="menu-img" src="https://img.icons8.com/ios-glyphs/200/FFE500/menu--v1.png" alt="">
        </div>
        <h1 id="logo-text">Logo</h1>
        <div id="control-btn-group">
            <button id="circle-btn" style="background-color: #1FFF43;"></button>
            <button id="circle-btn" style="background-color: #FBFF3E;"></button>
            <button id="circle-btn" style="background-color: #FF3030;"></button>
        </div>
    </div>
</template>


<style>
    #header-container {
        background-color: #303030;
        width: 100%;
        height: 60px;
        display: flex;
        align-items: center;
    }

    #control-btn-group {
        height: 40%;
        width: 81px;
        padding: 0 0 0 3px;
        margin: 0 15px 0 auto;
        display: flex;
        align-items: center;
        gap: 10px;
    }

    #circle-btn {
        border-radius: 100%;
        width: 18px;
        height: 18px;
        border: 0;
        opacity: 0.7;
        transition: opacity 0.3s, width 0.1s, height 0.1s, margin 0.1s;
    }

    #circle-btn:hover {
        transition: opacity 0.3s, width 0.1s, height 0.1s, margin 0.1s;
        opacity: 1;
    }

    #circle-btn:active {
        width: 16px;
        height: 16px;
        margin: 1px 1px 1px 1px;
        transition: width 0.1s, height 0.1s, margin 0.1s;
    }

    #contact-btn {
        margin: 0 auto 0 auto;
        width: 160px;
        background-color: #565656;
        color: white;
        border: 0;
    }

    #menu-group {
        width: 81px;
        height: 85%;
        margin: 0 auto 0 15px;
        display: flex;
        align-items: center;
    }

    #menu-img {
        height: 35px;
        width: 35px;
        opacity: 0.7;
        transition: opacity 0.3s, transform 0.5s;
    }

    #menu-img:hover {
        transition: opacity 0.3s, transform 0.5s;
        opacity: 1;
    }

    #menu-img:active {
        transition: transform 0.5s;
    }

    #logo-text {
        color: white;
        font-family: Georgia, 'Times New Roman', Times, serif;
    }

</style>