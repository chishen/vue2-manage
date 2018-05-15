<template>
    <div class="fillcontain">
        <head-top></head-top>
        <div class="table_container">
            蜜蜂团队
        </div>
    </div>
</template>
<script>
    import headTop from '../components/headTop'
    export default {
        data(){
            return {

            }
        },
        components: {
            headTop,
        },
    }
</script>

<style lang="less" scoped rel="stylesheet/less">
    @import '../style/mixin';
    .table_container{
        padding: 20px;
    }
</style>
