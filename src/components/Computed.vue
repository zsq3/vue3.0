<template>
  <div>
     <h3>computed测试： 只读计算属性：{{resetCount}}， 可读写的计算属性： {{plusCount}}</h3>
  </div>
</template>

<script>
  import { computed, ref } from '@vue/composition-api'


  export default {
        setup(){
            const count = ref(0);
            //1. 创建只读的计算属性
            const resetCount = computed(() => ++count.value);

            //2. 创建可读可写的计算属性
            const plusCount = computed({
              //取值
              get(){
                return count.value
              },
              //赋值
              set(val){
                return count.value += val
              }
            });
            //plusCount返回ref结构对象
            plusCount.value = 10;  //赋值触发set函数,





            return { resetCount, plusCount }
        }
    }
</script>

<style scoped>

</style>
