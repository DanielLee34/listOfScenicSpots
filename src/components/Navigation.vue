<template>
    <div class="e-navigation__wrapper">
        <p class="e-navigation__page">美食頁次{{(nowPage+1)}}/{{totalPage}}</p>
        <div class="e-navigation__btn-group">
            <button
                v-for="(item, index) in totalPage"
                :key="index"
                @click="goTo(index)"
                class="e-btn__nav"
                :class="{'e-btn__nav--active' : nowPage === index}"
            >{{item}}</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Navigation',
    props: ['totalPage', 'nowPage'],
    methods: {
        goTo(val) {
            this.$emit('update:nowPage', val);
        },
    },
};
</script>
