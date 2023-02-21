<template>
    <div class="description-container">
        <div class='description'>
            <slot name='video-panel-title'>
                <H1> {{ title }} </H1>
                <span> {{ name }} </span>
                <H3> {{ subtitle }} </H3>
            </slot>
        </div>
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

    .description-container {
        position: absolute;

        display: flex;
        align-items: center;

        width:  100%;
        height:  100%;
        
        max-width: 1440px;
        max-height: 720px;

        padding-left: 4%;

    }

    .description {
        z-index: 4;

        text-align: center;
        font-size: 32px;
        color: aliceblue;
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

    @media (max-width: 390px) {
        .description-container {
            align-items: baseline;
            justify-content: center;
            top: 0;
            margin-top: 16%;
        }

        .description {
            font-size: 20px;
        }
        .description h1 { 
            font-size: 20px;
        }

        .description h3 {
            font-size: 20px;
        }

        .description span {
            font-size: 32px;
        }
    }

</style>