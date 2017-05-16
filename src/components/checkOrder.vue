<template>
    <div>
        <this-dialog :is-show="isShowCheckDialog" @on-close="">
            请检查你的支付状态
            <div class="button" @click="">
                支付成功
            </div>
            <div class="button" @click="">
                支付失败
            </div>
        </this-dialog>
        <this-dialog :is-show="isShowSuccessDialog" @on-close="">
            购买成功
        </this-dialog>
        <this-dialog :is-show="isShowFailDialog" @on-close="">
            购买失败
        </this-dialog>
    </div>
</template>

<script>
import Dialog from './dialog'
export default {
    components: {
        thisDialog: Dialog
    },
    props: {
        isShowCheckDialog: {
            type: Boolean,
            default: false
        }
    },
    data() {
        return {
            isShowSuccessDialog: false,
            isShowFailDialog: false
        }
    },
}
</script>

<style scoped>

</style>


