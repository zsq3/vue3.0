<template>
    <div>

    </div>
</template>

<script>
    import { watch, ref, reactive } from '@vue/composition-api'
    export default {
        setup(){
            const count = ref(1);
            const state = reactive({ name: 'pig', age: 10 });

            //监听单个ref数据
            watch(count, (cur, pre) => {
              console.log(cur, pre)   //当前的值， 之前的值

            }, {lazy: true});  // lazy: true 使 watch 在被刚创建的时候，不执行回调函数中的代码


            //监听多个ref数据     目前不知道这里怎么深度(deep)监听。。
            const id = ref(2);
            watch([count, id], ([count, id], [prevCount, pid]) => {

            },{lazy: true});


            //监听单个reactive数据
            watch(() => state.age, () => { console.log('年龄改变了')}, {lazy: true});


            //监听多个reactive数据
            const watchData = [() => state.name, () => state.age];
            watch(watchData, ([name, age], [prevName, prevAge]) => {

                console.log(`当前name${name},当前age:${age}`);
                console.log(`曾经的name: ${prevName}, 曾经的age: ${prevAge}`)

            },{lazy: true});



            setTimeout(() => {
              count.value++;
              state.age++;
            },3000)
        }
    }
</script>

<style scoped>

</style>
