<template>
    <div class="character-container">
        <div class="character-image">
            <slot
            :src='url' 
            :alt='description'
            :width='image.size.width'
            :height='image.size.height'
            >
            </slot>
        </div>
    </div>
    
</template>

<script>
export default {
    props:[
        'url', 
        'description', 
        'width',
        'height'
    ],

    data() {
        return {
            image:{
                size:{
                    width: '480px',
                    height: '540px'
                }
            }
        }
    }
}
</script>

<style scoped>

    .character-container {
        max-width: 80%;
        width: 1440px;
        height: 720px;
        display: flex;
        flex-direction: row-reverse;
        position: absolute;
    }
    .character-image{
        position: fixed;
        width: 480px;
        height: 540px;
        z-index: 4;
    }

    .character-image img{
        width: 100%;
        height: 100%;
    }

</style>