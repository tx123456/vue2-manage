<template>
    <div class="fillcontain">
        <head-top></head-top>
        <div class="table_container">
            <el-table
                :data="tableData"
                border
                stripe
                class="content"
                style="width: 100%">
                <el-table-column type="expand">
                    <template slot-scope="props">
                        <el-form label-position="left" inline class="demo-table-expand">
                            <el-form-item label="费率">
                                <span>{{ props.row.rate }}</span>
                            </el-form-item>
                            <el-form-item label="最后登录时间">
                                <span>{{ props.row.lastTime }}</span>
                            </el-form-item>
                            <el-form-item label="审核时间">
                                <span>{{ props.row.auditTime }}</span>
                            </el-form-item>
                            <el-form-item label="创建时间">
                                <span>{{ props.row.createTime }}</span>
                            </el-form-item>
                        </el-form>
                    </template>
                </el-table-column>
                <el-table-column type="index" width="60"/>
                <el-table-column prop="phone" label="用户名" width="140"/>
                <el-table-column prop="sex" label="性别" width="70"/>
                <el-table-column prop="bankName" label="活体检测姓名" width="140"/>
                <el-table-column prop="realName" label="银行卡姓名" width="140"/>
                <el-table-column prop="address" label="定位地点" width="200"/>
                <el-table-column prop="allLimit" label="总额度" width="100"/>
                <el-table-column prop="surplusLimit" label="剩余额度" width="100"/>
                <el-table-column prop="auditType" label="审核状态" width="100"/>
                <el-table-column label="操作">
                    <template slot-scope="scope">
                        <el-button size="mini" @click="detail(scope.$index, scope.row)">详情</el-button>
                        <el-button size="mini" @click="sendMessage(scope.$index, scope.row)">下发消息</el-button>
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
            return{
                tableData:[{
                    phone: '17370484832',
                    sex: '男',
                    bankName: '王小虎',
                    realName: '王小虎',
                    rate: '费率1',
                    lastTime: '2016-05-02 15:56:23',
                    auditTime: '2016-05-02 15:56:23',
                    createTime: '2016-05-02 15:56:23',
                    allLimit: '3000.00',
                    surplusLimit: '1000.00',
                    auditType: '通过',
                    address: '上海市普陀区金沙江路 1518 弄'
                }],
                currentRow: null,
                offset: 0,
                limit: 200,
                count: 0,
                currentPage: 1
            }
        },
        created(){

        },
        components: {
            headTop,
        },
        methods:{
            detail(index, row) {
                console.log(index, row);
            },
            sendMessage(index, row) {
                console.log(index, row);
            }
        }
    }
</script>

<style lang="less">
    @import '../style/mixin';
    .demo-table-expand {
        font-size: 0;
    }
    .demo-table-expand label {
        width: 90px;
        color: #99a9bf;
    }
    .demo-table-expand .el-form-item {
        margin-right: 0;
        margin-bottom: 0;
        width: 50%;
    }
</style>
