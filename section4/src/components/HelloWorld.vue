<template>
  <div class="alert alert-primary">

    <!-- ①② -->
    <!-- <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <hr>
    <p>Number: {{ num }}</p>  -->
    
    <!-- ④getter setter -->
    <!-- <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <hr>
    <p class="h5">val: {{ val }}</p> -->
    <!-- aを入力するとbは、aを2で割って2条した数字 -->
    <!-- <div class="form-group text-left">
      <label for="">* 2:</label>
      <input type="number" v-model="a" class="form-control">
    </div> -->
    <!-- bを入力するとah、bの平方根の2倍 -->
    <!-- <div class="form-group text-left">
      <label for="">^ 2:</label>
      <input type="number" v-model="b" class="form-control">
    </div> -->

    <!-- ⑤ウォッチャ 四則演算の結果を監視する -->
    <!-- <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <hr>
    <div class="form-group text-left">
      <label>Value:</label>
      <input type="number" v-model="val" class="gorm-control">
    </div>
    <table class="bg-white table mt-4">
      <tr><th>add:</th><td>{{ add }}</td></tr>
      <tr><th>sub:</th><td>{{ sub }}</td></tr>
      <tr><th>multiple:</th><td>{{ multiple }}</td></tr>
      <tr><th>divide:</th><td>{{ divide }}</td></tr>
    </table> -->

    <!-- ⑥イベントの修飾子 -->
    <h1>{{ title }}</h1>
    <pre v-on:click="clear">{{ message }}</pre>
    <hr>
    <div id="out" class="out" v-on:click="a_event">A
      <div id="mid" class="mid" v-on:click.self="b_event">B
        <div id="in" class="in" v-on:click="c_event">C
        </div>
      </div>
    </div>

  </div>

</template>

<script>
export default {
  name: 'HelloWorld',
  // props: {
  //   title: String,
  //   // ①
  //   // num: Number,

  //   // ②
  //   // num: {
  //   //   type: Number,
  //   //   default: 100,
  //   //   validator: ( value ) => {
  //   //     // 3つの式が全部trueならtrue 整数で0以上100未満
  //   //     return value == parseInt( value ) && value >= 0 && value <= 100
  //   //   },
  //   // }
  // },

  //   // ③
  // data() {
    // return {
    //   message: 'バリデーション・チェック',
    // }
    
  // },

  // ④
  // data() {
  //   return {
  //     message: '算術プロパティの利用。',
  //     val: 0,
  //   }
  // },
  // computed: {
  //   a: {
  //     get() {
  //       return this.val * 2
  //     },
  //     set( value ) {
  //       this.val = Math.floor( value / 2 )
  //     },
  //   },
  //   b: {
  //     get() {
  //       return this.val * this.val
  //     },
  //     set( value ) {
  //       this.val = Math.floor( Math.sqrt( value ))
  //     },
  //   },
  // },
  // created() {
  //   this.val = 10
  // },

  // ⑤
  // data() {
  //   return {
  //     title: 'Watchers',
  //     message: '値の監視',
  //     val: 0,
  //     add: 0,
  //     sub: 0,
  //     multiple: 0,
  //     divide: 0,
  //   }
  // },
  // watch: {
  //   val( newVal, oldVal ) {
  //     console.log( oldVal + ' -> ' + newVal )
  //     this.val = newVal
  //     var val = parseInt( this.val ) //値を整数に
  //     this.add = Math.floor( val + 2 )
  //     this.sub = Math.floor( val - 2 )
  //     this.multiple = Math.floor( val * 2 )
  //     this.divide = Math.floor( val / 2 )
  //   }
  // },
  // created() {
  //   this.val = 6
  // },

  // ⑥
  data: function() {
    return {
      title: 'Event',
      message: 'イベントの伝播について。\n',
    }
  },
  methods: {
    a_event( event ) {
      this.message += "A-Event [" + event.target.id + ' → ' + event.currentTarget .id + "]\n"
    },
    b_event( event ) {
      this.message += "B-Event [" + event.target.id + ' → ' + event.currentTarget .id + "]\n"
    },
    c_event( event ) {
      this.message += "C-Event [" + event.target.id + ' → ' + event.currentTarget .id + "]\n"
    },
    clear() {
      this.message = 'イベントの伝播について。\n'
    }
  },
}
</script>
<style>
pre {
  font-size: 16pt;
  line-height: 1.25;
}
div.out {
  padding: 0px;
  background: #eee;
  width: 300px;
  height: 200px;
}
div.mid {
  padding: 0px;
  background: #ddd;
  width: 200px;
  height: 170px;
}
div.in {
  padding: 0px;
  background: #ccc;
  width: 100px;
  height: 140px;
}
</style>