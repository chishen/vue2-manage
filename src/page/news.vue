<template>
    <div class="fillcontain">
        <head-top></head-top>
        <div class="table_container">
            <el-button type="primary">新增新闻</el-button>
            <el-select v-model="shelf_value" placeholder="是否上架">
                <el-option
                    v-for="item in select_shelf"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value"
                    :disabled="item.disabled">
                </el-option>
            </el-select>
            <el-select v-model="top_value" placeholder="是否置顶">
                <el-option
                    v-for="item in select_top"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value"
                    :disabled="item.disabled">
                </el-option>
            </el-select>
            <div class="block">
                <el-date-picker
                    v-model="date_value"
                    type="daterange"
                    range-separator="至"
                    start-placeholder="开始日期"
                    end-placeholder="结束日期">
                </el-date-picker>
            </div>
            <el-input style="width: 200px;" v-model="search_value" placeholder="输入标题模糊查询"></el-input>
            <el-button type="primary" plain>查询</el-button>
            <el-button plain>重置</el-button>

            <el-table
                :data="tableData"
                style="width: 100%">
                <el-table-column
                    label="标题"
                    width="180">
                    <template slot-scope="scope">
                        <span style="margin-left: 10px">{{ scope.row.date }}</span>
                    </template>
                </el-table-column>
                <el-table-column
                    label="添加时间"
                    width="180">
                    <template slot-scope="scope">
                        <span style="margin-left: 10px">{{ scope.row.date }}</span>
                    </template>
                </el-table-column>
                <el-table-column
                    label="上/下架状态"
                    width="180">
                    <template slot-scope="scope">
                        <el-switch
                            v-model="scope.row.isShelf">
                        </el-switch>
                    </template>
                </el-table-column>
                <el-table-column
                    label="是否置顶"
                    width="180">
                    <template slot-scope="scope">
                        <el-switch
                            v-model="scope.row.isTop">
                        </el-switch>
                    </template>
                </el-table-column>
                <!--<el-table-column-->
                    <!--label="姓名"-->
                    <!--width="180">-->
                    <!--<template slot-scope="scope">-->
                        <!--<el-popover trigger="hover" placement="top">-->
                            <!--&lt;!&ndash;<p>姓名: {{ scope.row.name }}</p>&ndash;&gt;-->
                            <!--<p>住址: {{ scope.row.address }}</p>-->
                            <!--<div slot="reference" class="name-wrapper">-->
                                <!--&lt;!&ndash;<el-tag size="medium">{{ scope.row.name }}</el-tag>&ndash;&gt;-->
                            <!--</div>-->
                        <!--</el-popover>-->
                    <!--</template>-->
                <!--</el-table-column>-->
                <el-table-column label="操作">
                    <template slot-scope="scope">
                        <el-button
                            size="mini"
                            @click="handleSee(scope.$index, scope.row)">查看</el-button>
                        <el-button
                            size="mini"
                            @click="handleEdit(scope.$index, scope.row)">编辑</el-button>
                        <el-button
                            size="mini"
                            type="danger"
                            @click="handleDelete(scope.$index, scope.row)">删除</el-button>
                    </template>
                </el-table-column>
            </el-table>
        </div>
    </div>
</template>
<script>
    import headTop from '../components/headTop'
    export default {
        data(){
            return {
                select_shelf: [{
                    value: '',
                    label: '是否上架',
                }, {
                    value: '1',
                    label: '已上架',
                }, {
                    value: '2',
                    label: '未上架',
                }],
                shelf_value: '',
                select_top: [{
                    value: '',
                    label: '是否置顶',
                }, {
                    value: '1',
                    label: '已置顶',
                }, {
                    value: '2',
                    label: '未置顶',
                }],
                top_value: '',
                date_value: '',
                search_value: '',
                tableData: [{
                    title: '第一届蜜蜂帮帮运动会正式开启',
                    date: '2016-05-02',
                    isShelf: true,
                    isTop: true,
                    address: '上海市普陀区金沙江路 1518 弄'
                }, {
                    title: '第一届蜜蜂帮帮运动会正式开启',
                    date: '2016-05-04',
                    isShelf: true,
                    isTop: true,
                    address: '上海市普陀区金沙江路 1517 弄'
                }, {
                    title: '第一届蜜蜂帮帮运动会正式开启',
                    date: '2016-05-01',
                    isShelf: true,
                    isTop: true,
                    address: '上海市普陀区金沙江路 1519 弄'
                }, {
                    title: '第一届蜜蜂帮帮运动会正式开启',
                    date: '2016-05-03',
                    isShelf: true,
                    isTop: true,
                    address: '上海市普陀区金沙江路 1516 弄'
                }]
            }
        },
        components: {
            headTop,
        },
        methods: {
            handleSee(index, row) {
                console.log(index, row);
            },
            handleEdit(index, row) {
                console.log(index, row);
            },
            handleDelete(index, row) {
                console.log(index, row);
            }
        }
    }
</script>

<style lang="less" scoped rel="stylesheet/less">
    @import '../style/mixin';
    .table_container{
        padding: 20px;
    }
</style>
