<template>
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
</template>

<script>
export default {
  name: 'bottomContent',
  data () {
    return{}
  },
  created () {},
  methods: {}
}
</script>

<style scoped lang="scss">
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
</style>
