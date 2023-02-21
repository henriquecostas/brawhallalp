<template>
    <div class='corpo'>
        <router-view></router-view>
    </div>
</template>

<script>

export default {

}

</script>

<style>
    * {
        margin: 0px;
        padding:  0px;
        box-sizing: border-box;

    }

    html {

        width: 100vw;
        height: 100vh;
        margin: 0 auto;
        
    }

    body {

        width: 100%;
        height: 100%;
        
        margin: 0 auto;
        
        display: flex;
        justify-content: center;
        align-items: center;
        
        background-color: #182429;
        overflow: hidden;

    }

    .app {

        height: 100%;
        width: 100%;
        
        max-width: 1440px;
        max-height: 720px;

        display: flex;

        background-color: #1E1E1E;    
        border-radius: 8px;
        border: 1px solid #193c4b;

    }

    .static-bar {
        z-index: 1;

        display: flex;
        justify-content: center;
        align-items: center;
        
        width: 20%;
        
        background: linear-gradient(180deg, #182429 14.9%, #193C4B 82.08%);
        border-radius: 0px 8px 8px 0px;
    }

    .game-logo {
        min-width: 80%;
        padding: 20px;
    }

    /* .border-container {
        max-width: 1440px;
        width: 100%;
        height: 100%;
        position: absolute;
        z-index: 10;
    }

    .border-detail {
        position: fixed;
        right: 12.5vh;
        top: 50vh;
        mix-blend-mode: color-dodge;
        transform: matrix(0, -1, -1, 0, 0, 0);
    }

    .invert {
        transform: matrix(0, 1, -1, 0, 0, 0);
    } */

    .colorize {
        background: rgba(25, 60, 75, 0.27);
        width: 100%;
        height: 100%;
        position: absolute;
        max-width: 1440px;
        max-height: 720px;
        border-radius: 8px;
    }

    .panel {
        width: 100%;
        height: 100%;
        position: absolute;
        max-width: 1440px;
        max-height: 720px;
        border-radius: 8px;
    }

    .half-panel {
        width: 100%;
        height: 100%;
        position: absolute;
        max-width: 1222px;
        max-height: 720px;
        display: flex;
        flex-direction: row-reverse;
        align-items: center;
        border-radius: 8px;
    }

</style>