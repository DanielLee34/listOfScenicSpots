<template>
    <div>
        <section class="e-form__group">
            <select name="city" id="" v-model="cityNo" class="e-form__select">
                <option disabled value="0">請選擇行政區</option>
                <option
                    v-for="(item, index) in districtsData"
                    :key="index"
                    :value="index"
                >{{item.cityName}}</option>
            </select>
            <select name="districts" id="" v-model="townName" class="e-form__select">
                <option disabled value="0">請選擇鄉鎮區</option>
                <option
                    v-for="(item) in districts" :key="item.name"
                    :value="item.name"
                >{{ item.name }}</option>
            </select>
        </section>
    </div>
</template>
<script>
export default {
    name: 'FormSelect',
    props: ['parentTownName', 'parentCityNo', 'districtsData'],
    // props: {
    //     nowTownName: {
    //         type: String,
    //         default: '0',
    //     },
    //     nowCityNo: {
    //         type: Number,
    //         default: 0,
    //     },
    // },
    computed: {
        districts() {
            return this.districtsData[this.cityNo].districts;
        },
        cityNo: {
            get() {
                return this.parentCityNo;
            },
            set(val) {
                this.$emit('update:parentCityNo', val);
            },
        },
        townName: {
            get() {
                return this.parentTownName;
            },
            set(val) {
                this.$emit('update:parentTownName', val);
            },
        },
    },
};
</script>
