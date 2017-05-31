<template>
    <div class="order-wrap">
        <h3>您的产品</h3>
        <div class="order-list-choose">
            <div class="order-list-option">
                选择产品：
                <v-selection :selections="products" @on-change="productChange"></v-selection>
            </div>
        </div>
    </div>
</template>

<script>
import VSelection from '../components/base/selection'
export default {
    components: {
        VSelection
    },
    data() {
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
}
</script>

<style scopted>

</style>
