<template>
  <div>
    <h3>reactive响应式数据测试： 名字：{{name}}， 年龄：{{age}}</h3>
    <button @click="age++">年龄变大</button>
  </div>
</template>

<script>
  import {reactive} from '@vue/composition-api';


  export default {
    setup(){
      const state = reactive({     //reactive相当于vue2.x里的data(), 里面可以设置响应式数据
        name: 'dog',
        age: 2
      });

      return state     //都是返回一个对象， ref也是 return { xxx }
    }
  }
</script>

<style scoped>

</style>
