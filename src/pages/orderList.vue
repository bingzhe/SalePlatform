<template>
    <div class="order-wrap">
        <h3>您的产品</h3>
        <div class="order-list-choose">
            <div class="order-list-option">
                选择产品：
                <v-selection :selections="products" @on-change="productChange"></v-selection>
            </div>
            <div class="order-list-option">
                开始日期：
                <v-date-picker @on-change="getStartDate"></v-date-picker>
            </div>
            <div class="order-list-option">
                结束日期：
                <v-date-picker @on-change="getEndDate"></v-date-picker>
            </div>
            <div class="order-list-option">
                关键词：
            </div>
        </div>
    
    </div>
</template>

<script>
import VSelection from '../components/base/selection'
import VDatePicker from '../components/base/datepicker'
export default {
    components: {
        VSelection,
        VDatePicker
    },
    data() {
        return {
            query: '',
            projuctId: 0,
            startDate: '',
            endDate: '',
            products: [
                {
                    label: '数据统计',
                    value: 0
                },
                {
                    label: '数据预测',
                    value: 1
                },
                {
                    label: '流量分析',
                    value: 2
                },
                {
                    label: '广告发布',
                    value: 3
                }
            ]
        }
    },
    methods: {
        productChange(obj) {
            console.log(obj)
            this.productId = obj.value
            // this.getList()
        },
        getStartDate(date) {
            this.startDate = date
            // this.getList()
        },
        getEndDate(date) {
            this.endDate = date
            // this.getList()
        }
    }
}
</script>

<style scopted>
.order-wrap {
    width: 1200px;
    min-height: 800px;
    margin: 20px auto;
    overflow: hidden;
}

.order-wrap h3 {
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 20px;
}

.order-query {
    height: 25px;
    line-height: 25px;
    border: 1px solid #e3e3e3;
    outline: none;
    text-indent: 10px;
}

.order-list-option {
    display: inline-block;
    padding-left: 15px;
}

.order-list-option:first-child {
    padding-left: 0;
}

.order-list-table {
    margin-top: 20px;
}

.order-list-table table {
    width: 100%;
    background: #fff;
}

.order-list-table td,
.order-list-table th {
    border: 1px solid #e3e3e3;
    text-align: center;
    padding: 10px 0;
}

.order-list-table th {
    background: #4fc08d;
    color: #fff;
    border: 1px solid #4fc08d;
    cursor: pointer;
}

.order-list-table th.active {
    background: #35495e;
}
</style>
