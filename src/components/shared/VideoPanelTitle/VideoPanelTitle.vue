<template>
    <div class='description'>
        <slot name='video-panel-title'>
            <H1> {{ title }} </H1>
            <span> {{ name }} </span>
            <H3> {{ subtitle }} </H3>
        </slot>
    </div>
</template>

<script>
export default {
    props:[
        'name', 
        'title', 
        'subtitle'
    ],

    data() {
        return {

        }
    }
}
</script>

<style scoped>
    .description {
        position: absolute;
        margin-left: 124px;
        text-align: center;
        top: 40%;
        font-size: 32px;
        color: aliceblue;
        z-index: 4;
    }

    .description h1 {
        font-family: 'Lato', sans-serif;    
        font-size: 32px;
        font-weight: 900;
        padding-bottom: 8px;
    }

    .description h3 {
        font-family: 'Lato', sans-serif;
        font-weight: 300;
        font-size: 32px;
    }

    .description span {
        font-family: 'Lancelot', cursive;
        font-size: 48px;
        font-weight: 400;

        background: linear-gradient(180deg, #5198B4 24.48%, #1C3843 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }
</style>