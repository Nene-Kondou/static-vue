<template>
  <div class="alert alert-primary">

    <!-- ①② -->
    <!-- <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <hr>
    <p>Number: {{ num }}</p>  -->
    
    <!-- ④getter setter -->
    <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <hr>
    <p class="h5">val: {{ val }}</p>
    <!-- aを入力するとbは、aを2で割って2条した数字 -->
    <div class="form-group text-left">
      <label for="">* 2:</label>
      <input type="number" v-model="a" class="form-control">
    </div>
    <!-- bを入力するとah、bの平方根の2倍 -->
    <div class="form-group text-left">
      <label for="">^ 2:</label>
      <input type="number" v-model="b" class="form-control">
    </div>
  </div>

</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    title: String,
    // ①
    // num: Number,

    // ②
    // num: {
    //   type: Number,
    //   default: 100,
    //   validator: ( value ) => {
    //     // 3つの式が全部trueならtrue 整数で0以上100未満
    //     return value == parseInt( value ) && value >= 0 && value <= 100
    //   },
    // }
  },

  //   // ②
  // data() {
    // return {
    //   message: 'バリデーション・チェック',
    // }
    
  // },

  // ③
  data() {
    return {
      message: '算術プロパティの利用。',
      val: 0,
    }
  },
  computed: {
    a: {
      get() {
        return this.val * 2
      },
      set( value ) {
        this.val = Math.floor( value / 2 )
      },
    },
    b: {
      get() {
        return this.val * this.val
      },
      set( value ) {
        this.val = Math.floor( Math.sqrt( value ))
      },
    },
  },
  created() {
    this.val = 10
  },
}
</script>
