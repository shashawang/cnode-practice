<template>
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
  </div>
</template>

<script>
export default {
  name: 'sidebar',
  data () {
    return{}
  },
  created () {},
  methods: {}
}
</script>

<style scoped lang="scss">
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
</style>
