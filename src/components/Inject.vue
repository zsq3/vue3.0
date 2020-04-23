<template>
    <div>
        provide-inject测试接收到得数据为： {{ order }}
    </div>
</template>

<script>
    import { inject } from '@vue/composition-api'

    export default {
        setup(props, ctx){
            const order = inject('order');

            return { order }
        }
    }
</script>

<style scoped>

</style>
