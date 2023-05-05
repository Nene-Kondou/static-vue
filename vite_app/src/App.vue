<template>
  <div id="app">
    <!-- ① -->
    <!-- <HelloWorld title="Hello" /> -->

    <!-- ②親コンポーネントから子コンポーネントへ値を渡す タイトルを変更 -->
    <!-- <HelloWorld v-bind:title="message" />
    <hr>
    <button class="btn btn-primary" v-on:click="doAction">change title</button> -->

    <!-- ③子コンポーネントから親コンポーネントへ -->
    <HelloWorld v-bind:title="message" v-on:result-event="appAction" />
    <hr>
    <p>{{ result }}</p>

    <!-- ④テンプレート参照 -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },

  // ②
  // data() {
  //   return {
  //     message: 'HELLO',
  //   }
  // },
  // methods: {
  //   doAction() {
  //     var input = prompt( "new title:" )
  //     this.message = input
  //   }
  // },

  // ③
  data() {
    return {
      message: 'HELLO',
      result: 'no event',
    }
  },
  methods: {
    appAction( message ) {
      this.result = '(*** you send:"' + message + '". ***)'
    }
  },
}
</script>
