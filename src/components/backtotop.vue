<template>
      <div class="backtotop" style="top: 303px; right: 0px; display: block;">回到顶部</div>
      </div>
</template>

<script>
export default {
  name: 'backtotop',
  data () {
    return{
    }
  }
}
</script>

<style scoped lang="scss">
    .backtotop{
      position: fixed;
      width: 24px;
      color: gray;
      padding: 12px 0 12px 5px;
      cursor: pointer;
      text-align: center;
    }
</style>
