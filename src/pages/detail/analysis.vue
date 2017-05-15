<template>
    <div class="sales-board">
        <div class="sales-board-intro">
            <h2>流量分析</h2>
            <p>是指在获得网站访问量基本数据的情况下对有关数据进行统计、分析，从中发现用户访问网站的规律，并将这些规律与网络营销策略等相结合，从而发现目前网络营销活动中可能存在的问题，并为进一步修正或重新制定网络营销策略提供依据。当然这样的定义是站在网络营销管理的角度来考虑的</p>
        </div>
        <div class="sales-board-form">
            <div class="sales-board-line">
                <div class="sales-board-line-left">
                    购买数量：
                </div>
                <div class="sales-board-line-right">
                    <v-counter :max="numMax" @on-change="onParamChange('buyNum', $event)"></v-counter>
                </div>
            </div>
            <div class="sales-board-line">
                <div class="sales-board-line-left">
                    产品类型：
                </div>
                <div class="sales-board-line-right">
                    <v-selection :selections="buyTypes" @on-change="onParamChange('buyType', $event)"></v-selection>
                </div>
            </div>
            <div class="sales-board-line">
                <div class="sales-board-line-left">
                    有效时间：
                </div>
                <div class="sales-board-line-right">
                    <v-chooser :selections="periodList" @on-change="onParamChange('period', $event)"></v-chooser>
                </div>
            </div>
            <div class="sales-board-line">
                <div class="sales-board-line-left">
                    产品版本：
                </div>
                <div class="sales-board-line-right">
                    <v-mul-chooser :selections="versionList"></v-mul-chooser>
                </div>
            </div>
            <div class="sales-board-line">
                <div class="sales-board-line-left">
                    总价：
                </div>
                <div class="sales-board-line-right">
    
                </div>
            </div>
            <div class="sales-board-line">
                <div class="sales-board-line-left">
                    &nbsp;
                </div>
                <div class="sales-board-line-right">
                    <div class="button">
                        立即购买
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import VCounter from '../../components/base/counter'
import VSelection from '../../components/base/selection'
import VChooser from '../../components/base/chooser'
import VMulChooser from '../../components/base/multiplyChooser'
export default {
    components: {
        VCounter,
        VSelection,
        VChooser,
        VMulChooser
    },
    data() {
        return {
            numMax: 20,
            buyNum: 0, //购买数量
            buyTypes: [
                {
                    label: '入门版',
                    value: 0
                },
                {
                    label: '中级版',
                    value: 1
                },
                {
                    label: '高级版',
                    value: 2
                }
            ],
            periodList: [
                {
                    label: '半年',
                    value: 0
                },
                {
                    label: '一年',
                    value: 1
                },
                {
                    label: '三年',
                    value: 2
                }
            ],
            versionList: [
                {
                    label: '客户版',
                    value: 0
                },
                {
                    label: '代理商版',
                    value: 1
                },
                {
                    label: '专家版',
                    value: 2
                }
            ]
        }
    },
    methods: {
        onParamChange(attr, val) {
            console.log(val)
        }
    }
}
</script>

<style scoped>
.buy-dialog-title {
    font-size: 16px;
    font-weight: bold;
}

.buy-dialog-btn {
    margin-top: 20px;
}

.buy-dialog-table {
    width: 100%;
    margin-bottom: 20px;
}

.buy-dialog-table td,
.buy-dialog-table th {
    border: 1px solid #e3e3e3;
    text-align: center;
    padding: 5px 0;
}

.buy-dialog-table th {
    background: #4fc08d;
    color: #fff;
    border: 1px solid #4fc08d;
}
</style>

