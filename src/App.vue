<template>
  <!--跟 index.html 里的那个是没有关系的。这个 id=app 只是跟下面的 css 对应。-->
  <div id="app">
    <img src="./assets/logo.png">
    <!--意思是当前路由（ URL）指向的内容将显示在这个容器中-->
    <router-view/>
  </div>
</template>

<script>
  // ES6 的语法
export default {
  name: 'App'
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
