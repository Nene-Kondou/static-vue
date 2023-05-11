<template>
  <div id="app">
    <!-- ①slot -->
    <!-- <HelloWorld title="slot">
      <p>***this is defalut text***</p>
    </HelloWorld> -->

    <!-- ②名前付きスロット -->
    <!-- <HelloWorld>
      <p>Begin!..</p>
      <p>..Middle..</p>
      <p>..End</p>
      <template v-slot:first>
        ***First message***
      </template>
      <template v-slot:second>
        ***Second message***
      </template>
      <template v-slot:third>
        ***Third message***
      </template>
    </HelloWorld> -->

    <!-- ③スロットに値を設定する 親コンポーネント側の値を表示 -->
    <HelloWorld title="slot">
      <li class="list-group-item" v-for="obj in slotobjs" v-bind:key="obj.name">
        {{ obj.name }} {{ obj.mail }}
      </li>
    </HelloWorld>  
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  // ①②
  name: 'App',
  components: {
    HelloWorld
  },
  // ③
  data() {
    return {
      slotobjs: [
        { name: 'Taro', mail: 'taro@yamada'},
        { name: 'Hanako', mail: 'hanako@flower'},
        { name: 'Sachiko', mail: 'sachiko@happy'},
      ],
    }
  },
}
</script>
