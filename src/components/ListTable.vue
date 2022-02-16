<template>
    <div class="e-table__wrapper">
        <table class="e-table">
            <thead v-if="scenicListMax10.length !== 0" class="e-table__head">
                <tr>
                    <th scope="col">編號</th>
                    <th scope="col">行政區域</th>
                    <th scope="col">鄉鎮區</th>
                    <th scope="col">商家</th>
                    <th scope="col">地址</th>
                </tr>
            </thead>
            <tbody>
                <tr
                    v-for="(item, index) in scenicListMax10"
                    :key="item.ID"
                    class="e-table__body"
                >
                    <td scope="col" class="e-table__no">
                        {{ nowPage !== 0 ? (index+1) + (nowPage * 10) : index+1 }}
                    </td>
                    <td>{{item.City}}</td>
                    <td>{{item.Town}}</td>
                    <td>{{item.Name}}</td>
                    <td :title="item.Address">{{item.Address}}</td>
                </tr>
            </tbody>
        </table>
        <div v-if="scenicListMax10.length === 0" class="e-error">
            目前此分類無資料
        </div>
    </div>
</template>

<script>
export default {
    name: 'ListTable',
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
