<template>
  <div class="hello">
    <setup-test :page="page"></setup-test>
    <reactive-test></reactive-test>
    <ref-test></ref-test>
    <computed-test></computed-test>
    <watch-test></watch-test>
  </div>
</template>

<script>
  import ReactiveTest  from "@/components/Reactive";
  import SetupTest  from "@/components/Setup";
  import RefTest  from "@/components/Ref";
  import ComputedTest  from "@/components/Computed";
  import WatchTest  from "@/components/Watch";


  export default {
    components:{
      "setup-test": SetupTest,
      "reactive-test": ReactiveTest,
      "ref-test": RefTest,
      "computed-test": ComputedTest,
      "watch-test": WatchTest
    },
    data () {
      return {
        page: 10
      }
    }
}
</script>

<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
