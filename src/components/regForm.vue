<template>
    <div class="login-form">
        <div class="g-form">
            <div class="g-form-line">
                <span class="g-form-label"></span>
                <div class="g-form-input">
                    <input type="text" v-modal="" placeholder="请输入用户名">
                </div>
            </div>
            <div class="g-form-line">
                <div class="g-form-btn">
                    <a class="button">登录</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {

        }
    },
    computed: {
        userErrors () {
            let status, errorText
            if( !/@/g.test(this.usernameModal)){
                status = false
                errorText = "必须包含@"
            }
            else {
                status = true
                errorText = ''
            }
        }
    }
}
</script>

<style scoped>
    
</style>