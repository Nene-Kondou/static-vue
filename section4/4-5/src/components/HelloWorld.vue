<template>
  <div class="alert alert-primary">
    <!-- ①フェードインフェードアウト -->
    <!-- <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <button class="btn btn-primary m-3" v-on:click="doAction">
      {{ btn }}
    </button>
    <transition name="transit">
      <p v-if="flg" class="alert alert-light h5 trans">
        Trasition context!
      </p>
    </transition> -->

    <!-- ②イベントでメッセージを表示 -->
    <!-- <div class="hello">
      <h1>{{ title }}</h1>
      <p>{{ message }}</p>
      <hr>
      <button v-on:click="doAction">{{ btn }}</button>
      <transition name="transit" 
        v-on:before-enter="startAction"
        v-on:before-leave="startAction"
        v-on:after-enter="endAction"
        v-on:after-leave="endAction"
      >
      <p class="trans" v-if="flg">Transtion!</p>
      </transition>
    </div> -->

    <!-- ③transform -->
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <button class="btn btn-primary mb-3" v-on:click="doAction">Show/Hide</button>
    <transition name="transit">
      <p class="trans" v-if="flg">Transtion!</p>
      </transition>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  // ②
  // props: {
  //   title: String,
  // },


  data() {
    return {
      // ①
      // title: 'Trans&Anim',
      // message: 'This is Transition sample!',
      // flg: true,
      // btn: 'Show/Hide'

      // ②
      // message: 'Transition Sample!',
      // flg: true,
      // btn: 'Hide',

      // ③
      title: 'Trans&Anim',
      message: 'This is Transition sample!',
      flg: true,
      btn: 'Hide'
    }
  },
  // ①②③
  methods: {
    doAction() {
      this.flg = !this.flg
    },
    // ②
    // startAction: function() {
    //   if ( this.flg ) {
    //     this.message = '現れます…'
    //   } else {
    //     this.message = "消えます…"
    //   }
    // },
    // endAction: function() {
    //   if ( this.flg ) {
    //     this.btn = 'Hide'
    //     this.message = "現れました。"
    //   } else {
    //     this.btn = 'Show'
    //     this.message = "消えました。"
    //   }
    // },
  },
}
</script>
<style>
.trans {
  background: #000;
  color: #fff;
  padding: 10px;
  font-size: 20pt;
}
.transit-enter-active {
  transition: opacity 0.5s;
}
.transit-leave-active {
  transition: opacity 5s;
}
.transit-enter {
  opacity: 0;
}
.transit-enter-from {
  opacity: 0;
}
.transit-enter-to {
  opacity: 1;
}
.transit-leave {
  opacity: 1;
}
.transit-leave-to {
  opacity: 0;
}


/* ③ */
.transit-enter-active {
  transition: 1.0s;
}
.transit-leave-active {
  transition: 1.0s;
  opacity: 0.5;
}
.transit-enter,
.transit-leave-to {
  /* transform: translateX(200px) translateY(-200px); */
  /* transform: scale(5); */
  transform: rotateZ(360deg);
  opacity: 0.1;
}
</style>
