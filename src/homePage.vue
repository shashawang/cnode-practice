<template>
  <el-container>
    <el-header>
      <div>
        <img>

      </div>
      <div>
        <div @click="toFirstPage">首页</div>
        <div @click="toFreshManPage">新手入门</div>
        <div @click="toApiPage">API</div>
        <div @click="toAboutPage">关于</div>
        <div @click="toRegisterPage">注册</div>
        <div @click="toLoginPage">登录</div>
      </div>
    </el-header>
    <el-container>
      <el-main>
        <el-table :data="tableData" style="width: 100%">
          <el-table-column prop="date" label="全部" @click="getAllInfo">
          </el-table-column>
          <el-table-column prop="name" label="精华" @click="">
          </el-table-column>
          <el-table-column prop="address" label="分享" @click="">
          </el-table-column>
          <el-table-column prop="date" label="问答" @click="">
          </el-table-column>
          <el-table-column prop="name" label="招聘" @click="">
          </el-table-column>
          <el-table-column prop="address" label="客户端测试" @click="">
          </el-table-column>
        </el-table>
        <el-pagination
          layout="prev, pager, next"
          :total="1000">
        </el-pagination>
      </el-main>
      <el-aside>
        <div id="sidebar">

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
      </el-aside>
    </el-container>
    <el-footer>
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
    </el-footer>
  </el-container>
</template>

<script>
export default {
  name: 'App',
  data: {},
  methods: {
    toFirstPage () {},
    toFreshManPage () {},
    toApiPage () {},
    toAboutPage () {},
    toRegisterPage () {},
    toLoginPage () {},
    getAllInfo () {}
  }
}
</script>

