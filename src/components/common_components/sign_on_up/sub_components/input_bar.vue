<template>
    <div class="input_bar">
        <div class="input-group input_group">
<!--             <div class="input_icon">
                <i class="fa fa-envelope fa-fw"></i>
            </div> -->
            <input class="form-control text_input"
                   type="text"
                   v-model="login"
                   placeholder="请输入手机/邮箱">
        </div>
        <div class="input-group input_group">
<!--           <div class="input_icon">
            <i class="fa fa-lock fa-fw"></i>
          </div> -->
          <input class="form-control text_input"
                 type="password"
                 v-model="password"
                 placeholder="请输入密码">
        </div>
    </div>
</template>

<script type="text/javascript">
export default {
    data () {
        return {
            login: '',
            password: ''
        }
    },
    computed: {
        sign_on_info: function () {
            return {
                'login': this.login,
                'password': this.password
            }
        }
    },

    watch: {
        sign_on_info (info) {
            this.$emit('signOnInfo', info)
        }
    }
 }
</script>

<style type="text/css">
.input_group {
    display: flex;
    margin-bottom: 15px;
}

.input_icon {
    font-size: 14px;
    padding: 6px 12px;
    color: #555;
    text-align: center;
    background: #eee;
    border: 1px solid #ccc;
    border-radius: 4px;
    border-right: 0;
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
}

.text_input {
    font-size: 14px;
}

.text_input::placeholder {
    color: #c6c6c6;
}

.text_input:focus {
    box-shadow: none;
    border-color: #08bf91;
}

</style>
