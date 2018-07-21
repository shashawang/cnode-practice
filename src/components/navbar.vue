<template>
<div class="navbar">
  <div class="leftNavbar">
    <a href="/">
      <img class="brand" src="//o4j806krb.qnssl.com/public/images/cnodejs_light.svg">
    </a>
    <input class="searchInput" v-model="inputText" @keyup.enter="search"/>
  </div>
  <div class="rightNavbar">
    <ul>
      <li class="navbarList" @click="toFirstPage">首页</li>
      <li class="navbarList" @click="toFreshManPage">新手入门</li>
      <li class="navbarList apiText" @click="toApiPage">API</li>
      <li class="navbarList" @click="toAboutPage">关于</li>
      <li class="navbarList" @click="toRegisterPage">注册</li>
      <li class="navbarList" @click="toLoginPage">登录</li>
    </ul>
  </div>
</div>
</template>

<script>
export default {
  name: 'navbar',
  data () {
    return{
      inputText: ''
    }
  },
  created () {},
  methods: {
    search () {}
  }
}
</script>

<style scoped lang="scss">
.navbar{
  width:100%;
  height: 50px;
  background-color: #333;
  .leftNavbar{
    .brand{
      display: inline-block;
      float: left;
      width: 120px;
      height: 28px;
      padding: 3px 20px;
      margin-left: 30px;
    }
    .searchInput{
      border-radius: 10px;
      display: inline-block;
      float: left;
      width: 233px;
      // border-radius: 10%;
      padding: 3px 5px 3px 22px;
      border: 0;
      margin-top: 12px;
      // font-size: 13px;
      // font-weight: 400;
      // line-height: 1;
    }
  }
  .rightNavbar{
    display: inline-block;
    float: right;
    margin-right: 56px;
    .navbarList{
      display: inline-block;
      float: left;
      margin-right: 30px;
      height: 40px;
      list-style: none;
      text-shadow: none;
      color: #ccc;
      font-size: 13px;
    }
    .apiText{
      margin-top: 2px;
    }
  }
}
</style>
