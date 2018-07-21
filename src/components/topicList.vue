<template>
  <div class="content">
    <ul class="header">
          <li class="headerList" @click="getAllTopicList">全部</li>
          <li class="headerList" @click="getGoodList">精华</li>
          <li class="headerList" @click="getShareList">分享</li>
          <li class="headerList" @click="getAskList">问答</li>
          <li class="headerList" @click="getJobList">招聘</li>
        </ul>
    <div class="table" v-for="item in tableData">
      <img class="portrait" @click="er.push({name: ''})" :src="item.author.avatar_url" alt="">
      <div class="replyVSview">{{ `${item.reply_count}/${item.visit_count}` }}</div>
      <div class="tab">{{ item.tab }}</div>
      <div class="title" @click="this.$router.push({name: ''})">{{ item.title }}</div>
      <!-- <img class="replierPortrait" :src="aaa" alt=""> -->
      <div class="replyTime">{{ }}</div>
    </div>
    <el-pagination
      layout="prev, pager, next"
      :total="1000">
    </el-pagination>
  </div>
</template>

<script>
const axios = require('axios');
const host = 'https://cnodejs.org/api/v1'

export default {
  name: 'topicList',
  data () {
    return{
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
</style>
