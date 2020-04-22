<template>
    <div>
        <h3>ref响应式数据测试：  姓名：{{person.name}}</h3>
        <input type="text" v-model="count">
        <button @click="count++">count+1</button>
    </div>
</template>

<script>
    import {ref} from '@vue/composition-api';
    export default {
        setup(){
          //ref与reactive都可以创建响应式数据
          // ref类似react hook的useState
          // const [count, setCount] = useState(0)
          //ref创建的响应式对象只包含一个value属性

          const person = ref({ name: 'cat', age: 3});  //ref()可以传对象，字符串等
          // person = {value: {name:'cat', age: 3}}

          const count = ref(1); //初始值1  count = { value: 1 }

          return {
            person,
            count
          }

          // toRefs()   isRef()  目前感觉没啥用处就不写了
        }
    }
</script>

<style scoped>

</style>
