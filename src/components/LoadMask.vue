<template>
    <div class="e-load__bg">
        <img src="https://media.giphy.com/media/l3nWhI38IWDofyDrW/giphy.gif" class="e-load__img" alt="">
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
            background-color: rgba($color: #bdb9b9, $alpha: 0.8);
            // background-color: rgba($color: #000000, $alpha: 0.8);
            // background-color: rgba($color: #000000, $alpha: 1);
            position: fixed;
            top: 0;
            left: 0;
        }
        &__img{
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            // width: 800px;
            opacity: 0.9;

            // https://media.giphy.com/media/3y0oCOkdKKRi0/giphy.gif
            // https://media.giphy.com/media/Vk7VKS50xcSC4/giphy.gif
            // https://media.giphy.com/media/3o7btTODQcZhN6eLQs/giphy.gif
            // https://media.giphy.com/media/l3nWhI38IWDofyDrW/giphy.gif
        }
    }
</style>
