<template>
  <div class="alert alert-info">
    <h2>{{ title }}</h2>
    <p>{{ message }}</p>

    <!-- ②v-onによるイベントの利用 -->
    <hr>
    <div>
      <input type="tel" class="form-control" v-model="input">
      <button class="btn btn-info mt-2" v-on:click="doAction">Click</button>
    </div>

    <!-- ④テンプレート参照 -->
    <!-- <h1>{{ title }}</h1>
    <p ref="msg">{{ message }}</p>
    <button class="btn btn-primary" v-on:click="DoAction">Click</button> -->

  </div>

</template>

<script>
export default {
  name: 'HelloWorld',
  // ①②③
  props: {
    title: String,
    message: String,
  },
  data() {
    return {
      message: 'お名前は？',
      input: 'no name',
    }
  },
  methods: {
    doAction() {
      // ①
      this.message = 'こんにちは、' + this.input + 'さん！'
      // ②
      this.$emit( 'result-event', this.input )
    }
  },

  // ④
  // data() {
  //   return {
  //     title: 'HelloWorld',
  //     message: 'This is sample message.'
  //   }
  // },
  // mounted() {
  //   this.counter = 0
  // },
  // methods: {
  //   DoAction() {
  //     // pタグにh6タグを追加している
  //     this.counter++
  //     this.$refs.msg.innerHTML += '<h6>counted: ' + this.counter + '</h6>'
  //   }
  // },
}
</script>
