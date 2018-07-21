<template>
    <div class="main">
      <topicList />
      <div style="flex:1"></div>
      <sidebar />
      <backtotop />
    </div>
</template>

<script>
import topicList from '@/components/topicList'
import sidebar from '@/components/sidebar'
import backtotop from '@/components/backtotop'

export default {
  name: 'mainContent',
  components: {topicList, sidebar, backtotop},
  data () {
    return{
    }
  }
}
</script>

<style scoped lang="scss">
  .main{
    display: flex;
    width: 90%;
    max-width: 1400px;
    min-width: 960px;
    margin: 15px auto;
    min-height: 400px;
  }
</style>
