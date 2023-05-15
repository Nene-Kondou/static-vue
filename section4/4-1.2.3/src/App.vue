<template>
  <div id="app">
    <!-- <HelloWorld v-bind:title="message" v-bind:num="num" />  -->
    <HelloWorld title="computed" /> 
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  data() {
    return {
      message: 'validate',
      num: 100 // 子コンポーネントでnumにはNumberを指定しているのにabcが表示される 
    }
  }
}
</script>
