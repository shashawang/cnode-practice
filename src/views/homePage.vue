<template>
  <div class="container">
    <navbar />
    <mainContent />
    <bottomContent />
  </div>
</template>

<script>
import navbar from '@/components/navbar'
import mainContent from '@/components/mainContent'
import bottomContent from '@/components/bottomContent'

export default {
  // name: 'App',
  components: {navbar, mainContent, bottomContent},
  data () {
    return{
    }
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
}
</style>
