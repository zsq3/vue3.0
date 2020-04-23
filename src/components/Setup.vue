<template>
    <div>
        <h3>接收到的父组件数据： {{page}}</h3>
        <ject-test></ject-test>
    </div>
</template>

<script>
  import {provide, onMounted, onUpdated, onUnmounted} from '@vue/composition-api';
  import Ject from "@/components/Inject";


  export default {
      components: {
         "ject-test": Ject
      },
      props: {
          page: Number
      },
      beforeCreate(){
        console.log('先执行')
      },

      setup(props, ctx){  //执行顺序在 beforeCreate和created 之间
        console.log(props.page, ctx); //setup中无法访问this, 用 ctx 代替
        provide('order', '上级传给下级得数据');

        onMounted(() => {
           //ctx.refs.xx
        });
        onUnmounted(() => {
           //clearInterval(ctx.xx.timer)
        })

      },

      created(){
        console.log('后执行')
      }
    }
</script>

<style scoped>

</style>
