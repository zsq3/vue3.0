<template>
    <div>
        <h3>接收到的父组件数据： {{page}}</h3>
    </div>
</template>

<script>
    export default {
      props: {
          page: Number
      },
      beforeCreate(){
        console.log('先执行')
      },

      setup(props, ctx){  //执行顺序在 beforeCreate和created 之间
        console.log(props.page, ctx); //setup中无法访问this, 用 ctx 代替
      },

      created(){
        console.log('后执行')
      }
    }
</script>

<style scoped>

</style>
