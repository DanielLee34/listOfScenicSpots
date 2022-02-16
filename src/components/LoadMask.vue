<template>
    <div class="e-load__bg">
        <img src="https://media.giphy.com/media/lPcbCcPfACi3ncc3cv/giphy.gif" class="e-load__icon" alt="">
    </div>
</template>
<script>
export default {
    name: 'LoadMask',
};
</script>
<style lang="scss" scoped>
    .e-load{
        &__bg{
            width: 100vw;
            height: 100vh;
            background-color: rgba($color: #000000, $alpha: 0.8);
            position: fixed;
            top: 0;
            left: 0;
        }
        &__icon{
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
        }
    }
</style>
