<template>
    <div>
        <section>
            <div
                v-for="(item) in scenicListMax10"
                :key="item.ID"
                class="e-card-type01__wrapper container"
            >
                <!-- <img :src="item.PicURL" class="e-card-type01__img" :alt="item.Name"> -->
                <div
                    class="e-card-type01__img"
                    :style="{'background-image': 'url(' + item.PicURL + ')'}"
                ></div>
                <div class="e-card-type01__group">
                    <!-- <a v-if="item.BlogUrl == ''" :href="item.BlogUrl" target="_blank">
                        <h2 class="mb-1 mb-md-2 mt-1">{{item.Name}}</h2>
                    </a> -->
                    <h2 class="mb-1 mb-md-2 mt-1">{{item.Name}}</h2>
                    <div class="e-card-type01__districts">
                        <h3>{{item.City}}</h3>
                        <h3>{{item.Town}}</h3>
                    </div>
                    <article v-html="item.HostWords" class="e-card-type01__article"></article>
                </div>
            </div>
            <div v-if="scenicListMax10.length === 0" class="e-error">
                目前此分類無資料
            </div>
        </section>
    </div>
</template>

<script>
export default {
    name: 'List',
    props: {
        scenicList: {
            type: Array,
            required: true,
        },
        nowPage: {
            type: Number,
        },
    },
    computed: {
        scenicListMax10() {
            return this.scenicList.slice(this.nowPage * 10, (this.nowPage * 10) + 10);
        },
    },
};
</script>

<style scoped lang='scss'>

</style>
