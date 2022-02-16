<template>
    <div>
        <section class="e-card-type02__wrapper">
            <div
                v-for="(item) in scenicListMax10"
                :key="item.ID"
                class="e-card-type02__body"
                :style="{'background-image': 'url(' + item.PicURL + ')'}"
            >
                <div class="e-card-type02__info">
                    <div class="e-card-type02__info-group">
                        <h3>{{item.City}}</h3>
                        <h3>{{item.Town}}</h3>
                    </div>
                    <h2 class="e-card-type02__name">{{item.Name}}</h2>
                    <article
                        v-html="item.HostWords"
                        class="e-card-type02__article"
                        :title="item.HostWords"
                    ></article>
                </div>
            </div>
        </section>
        <div v-if="scenicListMax10.length === 0" class="e-error">
            目前此分類無資料
        </div>
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
