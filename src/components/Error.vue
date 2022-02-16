<template>
    <div v-if="scenicList.length === 0" class="e-error">
        目前此分類無資料
    </div>
</template>
<script>
export default {
    name: 'error',
    props: ['scenicList'],
};
</script>
