<template>
  <div>
    用户名:<input type="text" v-model="loginForm.username" placeholder="请输入用户名"/>
    <br><br>
    密码： <input type="password" v-model="loginForm.password" placeholder="请输入密码"/>
    <br><br>
    <button v-on:click="login">登录</button>
  </div>
</template>

<script>
  export default {
    name: "Login",
    data() {
      return {
        loginForm: {
          username: '',
          password: ''
        },
        responseResult: []
      }
    },
    methods: {
      login() {
        this.$axios.post('login', {
          username: this.loginForm.username,
          password: this.loginForm.password
        })
          .then(successResponse => {
            //比较的同时，还看数据类型是否一致
            if (successResponse.data.code === 200) {
              //没有前后历史页
              this.$router.replace({path: '/index'})
            }
          })
          .catch(failResponse => {

          })
      }
    }
  }
</script>

<style scoped>

</style>
