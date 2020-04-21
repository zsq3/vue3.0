<template>
    <div>
        <h3>reactive响应式数据测试： 名字：{{name}}， 年龄：{{age}}</h3>
        <button @click="age++">年龄变大</button>
    </div>
</template>

<script>
  import {reactive} from '@vue/composition-api';


    export default {
      setup(props, ctx){  //执行顺序在 beforeCreate和created 之间
        console.log(props, ctx); //ctx = this
        const state = reactive({     //reactive相当于vue2.x里的data(), 里面可以设置响应式数据
            name: 'dog',
            age: 2
        });

        return state
      },

      created(){
        console.log('后执行')
      }
    }
</script>

<style scoped>

</style>
