<template>
    <div class="character-image">
        <slot
            :src='url' 
            :alt='description'
            :width='image.size.width'
            :height='image.size.height'
        >
        </slot>
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
    .character-image{
        position: absolute;
        margin-left: 60%;
        top: 20%;
        width: 480px;
        height: 540px;
        z-index: 4;
    }

    .character-image img{
        width: 100%;
        height: 100%;
    }

</style>