<template>
  <div class="container">
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
    <div class="main">
      <div class="content">
        <ul class="header">
          <li class="headerList" @click="getAllTopicList">全部</li>
          <li class="headerList" @click="getGoodList">精华</li>
          <li class="headerList" @click="getShareList">分享</li>
          <li class="headerList" @click="getAskList">问答</li>
          <li class="headerList" @click="getJobList">招聘</li>
        </ul>
        <div class="table" v-for="item in tableData">
          <img class="portrait" @click="this.$router.push({name: ''})" :src="item.author.avatar_url" alt="">
          <div class="replyVSview">{{ `${item.reply_count}/${item.visit_count}` }}</div>
          <div class="tab">{{ item.tab }}</div>
          <div class="title" @click="this.$router.push({name: ''})">{{ item.title }}</div>
          <img class="replierPortrait" :src="aaa" alt="">
          <div class="replyTime">{{ }}</div>
        </div>
        <el-pagination
          layout="prev, pager, next"
          :total="1000">
        </el-pagination>
      </div>
      <div style="flex:1"></div>
      <div class="sidebar">
        <div class="panel">
          <div class="inner">
            <p>CNode：Node.js专业中文社区</p>
            <div>
              您可以
              <a href="/signin">登录</a>
              或
              <a href="/signup">注册</a>
              , 也可以
              <a href="/auth/github">
                <span class="span-info">
                  通过 GitHub 登录
                </span>
              </a>
            </div>
          </div>
        </div>
        <div class="panel">
          <div class="header">
            <span class="col_fade">无人回复的话题</span>
          </div>
          <div class="inner">
            <ul class="unstyled">
              <li>
                <div><a class="dark topic_title" href="/topic/5b4c66d72b3325cc0f8398cd" title="npm 的包引用和管理使人感到担忧">npm 的包引用和管理使人感到担忧</a>
                </div>
              </li>
              <li>
                <div><a class="dark topic_title" href="/topic/5b4c0dd235342ab069061567" title="最近在学习hapi，请问有用hapi.js开发项目的吗？">最近在学习hapi，请问有用hapi.js开发项目的吗？</a>
                </div>
              </li>
              <li>
                <div><a class="dark topic_title" href="/topic/5b4b50a613ca2fe569fb93d4" title="Node.js 中的模块机制">Node.js 中的模块机制</a>
                </div>
              </li>
              <li>
                <div><a class="dark topic_title" href="/topic/5b4aae17e374eeab6929d6e2" title="nodeJS用户模块调用">nodeJS用户模块调用</a>
                </div>
              </li>
              <li>
                <div><a class="dark topic_title" href="/topic/5b49d3a0fb9e84ec69cc1a72" title="利用v8引擎实现运行js文件">利用v8引擎实现运行js文件</a>
                </div>
              </li>
            </ul>
          </div>
        </div>
        <div class="panel">
          <div class="header">
            <span class="col_fade">积分榜</span>
            &nbsp;
            <a class="dark" href="/users/top100">TOP 100 &gt;&gt;</a>
          </div>
          <div class="inner">
            <ol>
              <li>
                <span class="top_score">21140</span>
                <span class="user_name"><a href="/user/i5ting">i5ting</a></span>
              </li>
              <li>
                <span class="top_score">15005</span>
                <span class="user_name"><a href="/user/alsotang">alsotang</a></span>
              </li>
              <li>
                <span class="top_score">9350</span>
                <span class="user_name"><a href="/user/leapon">leapon</a></span>
              </li>
              <li>
                <span class="top_score">8760</span>
                <span class="user_name"><a href="/user/jiyinyiyong">jiyinyiyong</a></span>
              </li>
              <li>
                <span class="top_score">6930</span>
                <span class="user_name"><a href="/user/yakczh">yakczh</a></span>
              </li>
              <li>
                <span class="top_score">6540</span>
                <span class="user_name"><a href="/user/im-here">im-here</a></span>
              </li>
              <li>
                <span class="top_score">6135</span>
                <span class="user_name"><a href="/user/atian25">atian25</a></span>
              </li>
              <li>
                <span class="top_score">6015</span>
                <span class="user_name"><a href="/user/DevinXian">DevinXian</a></span>
              </li>
              <li>
                <span class="top_score">5315</span>
                <span class="user_name"><a href="/user/magicdawn">magicdawn</a></span>
              </li>
              <li>
                <span class="top_score">4740</span>
                <span class="user_name"><a href="/user/captainblue2013">captainblue2013</a></span>
              </li>
            </ol>
          </div>
        </div>
        <div class="panel">
          <div class="header">
            <span class="col_fade">友情社区</span>
          </div>
          <div class="inner">
            <ol class="friendship-community">
              <li>
                <a href="https://ruby-china.org/" target="_blank">
                  <img src="//o4j806krb.qnssl.com/public/images/ruby-china-20150529.png">
                </a>
              </li>
              <div class="sep10"></div>
              <li>
                <a href="http://golangtc.com/" target="_blank">
                  <img src="//o4j806krb.qnssl.com/public/images/golangtc-logo.png">
                </a>
              </li>
              <div class="sep10"></div>
              <li>
                <a href="http://phphub.org/" target="_blank">
                  <img src="//o4j806krb.qnssl.com/public/images/phphub-logo.png">
                </a>
              </li>
              <div class="sep10"></div>
              <li>
                <a href="https://testerhome.com/" target="_blank">
                  <img src="//dn-cnode.qbox.me/FjLUc7IJ2--DqS706etPQ1EGajxK">
                </a>
              </li>
            </ol>
          </div>
        </div>
        <div class="panel">
          <div class="header">
            <span class="col_fade">客户端二维码</span>
          </div>
          <div class="inner cnode-app-download">
            <img width="200" src="//dn-cnode.qbox.me/FtG0YVgQ6iginiLpf9W4_ShjiLfU">
            <br>
            <a href="https://github.com/soliury/noder-react-native" target="_blank">客户端源码地址</a>
          </div>
        </div>
      <div class="backtotop" style="top: 303px; right: 0px; display: block;">回到顶部</div>
      </div>
    </div>
    <div class="footer">
      <div class="links">
        <a class="dark" href="/rss">RSS</a>
        |
        <a class="dark" href="https://github.com/cnodejs/nodeclub/">源码地址</a>
      </div>
      <div class="col_fade">
        <p>CNode 社区为国内最专业的 Node.js 开源技术社区，致力于 Node.js 的技术研究。</p>
        <p>服务器赞助商为
          <a href="http://www.ucloud.cn/?utm_source=zanzhu&amp;utm_campaign=cnodejs&amp;utm_medium=display&amp;utm_content=yejiao&amp;ytag=cnodejs_logo" target="_blank" class="sponsor_outlink" data-label="ucloud_bottom">
            <img src="//dn-cnode.qbox.me/FuIpEaM9bvsZKnQ3QfPtBHWQmLM9" title="ucloud" alt="ucloud" width="92px">
          </a>
          ，存储赞助商为
          <a href="http://www.qiniu.com/?ref=cnode" target="_blank" class="sponsor_outlink" data-label="qiniu_bottom">
            <img src="//dn-cnode.qbox.me/Fg0jtDIcTqVC049oVu5-sn6Om4NX" title="七牛云存储" alt="七牛云存储" width="115px">
          </a>
          ，由
          <a href="https://www.aliyun.com/product/nodejs?ref=cnode" target="_blank" class="sponsor_outlink" data-label="alinode_bottom">
            <img src="//dn-cnode.qbox.me/FpMZk31PDyxkC8yStmMQL4XroaGD" title="alinode" alt="alinode" height="54px" width="166px">
          </a>提供应用性能服务。
        </p>
        <p>新手搭建 Node.js 服务器，推荐使用无需备案的
          <a href="https://www.digitalocean.com/?refcode=eba02656eeb3">DigitalOcean(https://www.digitalocean.com/)</a>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
const axios = require('axios');
const host = 'https://cnodejs.org/api/v1'
export default {
  name: 'App',
  data () {
    return{
      inputText: '',
      tableData: [],
      params : {
        page: 1,
        limit: 100
      }
    }
  },
  created () {
    this.getTopics()
  },
  methods: {
    search () {},
    toFirstPage () {},
    toFreshManPage () {},
    toApiPage () {},
    toAboutPage () {},
    toRegisterPage () {},
    toLoginPage () {},
    getAllInfo () {},
    getTopics() {
      axios.get(host+'/topics', {params: this.params})
      .then(res => {
          if(res.status === 200) {
            this.tableData = res.data.data
            for(let item of this.tableData) {
              if(item.tab === 'ask'){
                item.tab = '问答'
              } else if(item.tab === 'share'){
                item.tab = '分享'
              } else if(item.tab === 'job'){
                item.tab = '招聘'
              } else {
                item.tab = '问答'
              }
            }
          }
        }
      )
      .catch(err => console.log(err))
    },
    getAllTopicList () {
      this.getTopics()
    },
    getGoodList () {
      this.params.tab = 'good'
      this.getTopics()
    },
    getShareList () {
      this.params.tab = 'share'
      this.getTopics()
    },
    getAskList () {
      this.params.tab = 'ask'
      this.getTopics()
    },
    getJobList () {
      this.params.tab = 'job'
      this.getTopics()
    },
    
  }
}
</script>

<style scoped lang="scss">
.container{
  display: flex;
  flex-direction: column;
  margin: -60px -7px -14px -8px;
  padding: 0;
  font-family: "Helvetica Neue","Luxi Sans","DejaVu Sans",Tahoma,"Hiragino Sans GB",STHeiti,sans-serif!important;
  font-size: 14px;
  word-break: break-word;
  line-height: 20px;
  color: #333;
  text-overflow: ellipsis;
  // width:100%;
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
  .main{
    display: flex;
    width: 90%;
    max-width: 1400px;
    min-width: 960px;
    margin: 15px auto;
    min-height: 400px;
    // max-width: 940.5px;
    .content{
      display: inline-block;
      padding: 0;
      margin-right: 105px;
      .header{
        display: flex;
        flex-direction: flex-start;
        list-style: none;
        padding: 10px;
        background-color: #f6f6f6;
        border-radius: 3px 3px 0 0;
        .headerList {
          color: #80bd01;
          margin: 0 10px;
          background-color: #fff;
          padding: 3px 4px;
          border-radius: 3px;
        }
      }
      .table{
        display: flex;
        flex-direction: flex-start;
        border-top: 1px solid f6f6f6;
        padding: 6px;
        font-size: 16px;
        .portrait{
          width: 30px;
          height: 30px;
          margin-right: 6px;
        }
      }
    }
    .sidebar{
      float: right;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      width: 290px;
      font-size: 14px;
      margin-bottom: 20px;
      .panel{
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        font-size: 13px;
        margin-bottom: 13px;
        text-align: left;
        .header{
          color: #51585c;
          background-color: #f6f6f6;
          padding: 10px;
          border-radius: 3px 3px 0 0;
          text-overflow: ellipsis;
          .col_fade{
            color: #444;
          }
          a.dark, a.dark:active, a.dark:link, a.dark:visited{
            color: #666;
            text-decoration: none;
          }
        }
        .inner{
          padding: 10px;
          line-height: 2em;
          text-overflow: ellipsis;
          ul{
            padding: 0;
            margin: 0 0 10px;
            list-style: none;
            line-height: 2em;
          }
          ol{
            margin: 4px 0;
            padding: 0;
            list-style: none;
            .top_score {
              line-height: 2em;
              color: gray;
              padding: 2px;
              margin-right: 10px;
            }
            .user_name {
              max-width: 120px;
              white-space: nowrap;
              vertical-align: middle;
            }
          }
          .friendship-community{
            img {
              width: 150px;
              vertical-align: middle;
            }
          }
          p{
            font-size: 14px;
            margin: 0 0 10px;
          }
          a{
            color: #778087;
            text-decoration: none;
            .span-info{
              display: inline-block;
              // float: none;
              padding: 3px 10px;
              border: none;
              margin: 0;
              font-size: 14px;
              cursor: pointer;
              letter-spacing: 2px;
              border-radius: 3px;
              line-height: 2em;
              color: #fff;
              background-color: #5bc0de;
            }
          }
          .unstyled{
            list-style: none;
          }
        }
        .cnode-app-download{
          a{
            margin-left: 55px;
          }
        }
      }
    }
    .backtotop{
      position: fixed;
      width: 24px;
      color: gray;
      padding: 12px 0 12px 5px;
      cursor: pointer;
      text-align: center;
    }
  }
  .footer{
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    width: 90%;
    max-width: 1400px;
    min-width: 960px;
    margin: 0 auto;
    padding: 20px 0;
    font-size: 13px;
    line-height: 2em;
    a.dark, a.dark:active, a.dark:link, a.dark:visited {
      color: #666;
      text-decoration: none;
    }
    .col_fade {
      color: #ababab;
      p{
        line-height: 20px;
        font-size: 14px;
        word-break: break-word;
        margin: 0 0 10px;
        text-align: left;
        a{
          color: #08c;
          text-decoration: none;
          image{
            max-width: 100%;
            vertical-align: middle;
          }
        }
      }
    }
  }
}
</style>
