<template>
    <div class="login-form">
        <div class="g-form">
            <div class="g-form-line">
                <span class="g-form-label">用户名：</span>
                <div class="g-form-input">
                    <input type="text" v-model="usernameModel" placeholder="请输入用户名">
                </div>
                <span class="g-form-error">{{ userErrors.errorText }}</span>
            </div>
            <div class="g-form-line">
                <span class="g-form-label">密码：</span>
                <div class="g-form-input">
                    <input type="password" v-model="passwordModel" placeholder="请输入密码">
                </div>
                <span class="g-form-error">{{ passwordErrors.errorText}}</span>
            </div>
            <div class="g-form-line">
                <div class="g-form-btn">
                    <a class="button">登录</a>
                </div>
            </div>
            <p></p>
        </div>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                usernameModel: '',
                passwordModel: ''
            }
        },
        computed: {
            userErrors () {
                //定义错误信息和状态
                let errorText, status
                //如果不匹配@时
                if ( !/@/g.test(this.usernameModel)){
                    status = false
                    errorText = '不包含@'
                }
                else {
                    status = true
                    errorText = ''
                }
                //返回信息
                return {
                    status,
                    errorText
                }
            },
            passwordErrors () {
                let errorText, status
                if (!/^\w{1,6}$/g.test(this.passwordModel)) {
                    status = false
                    errorText = '密码不是1-6位'
                }
                else {
                    status = true
                    errorText = ''
                } 
                return {
                    status,
                    errorText
                }
            }
        }
    }
</script>

<style scoped>
    
</style>