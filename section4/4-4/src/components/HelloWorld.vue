<template>
  <div class="alert alert-primary">
    <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <hr>
    <div class="alert alert-light">
      <!-- ①slot -->
      <!-- <h3>Inner Slot</h3>
      <slot />  -->
      
      <!-- ②名前付きスロットを使う -->
      <!-- <h3>Inner Slot</h3>
      <div class="alert alert-warning h5">
        <slot />
      </div>
      <ul class="list-group">
        <li class="list-group-item">
          <slot name="first" />
        </li>
        <li class="list-group-item">
          <slot name="second" />
        </li>
        <li class="list-group-item">
          <slot name="third" />
        </li>
      </ul> -->

      <!-- ③スロットに値を設定する -->
      <h3>Inner Slot</h3>
      <ol class="list-group text-left">
        <slot />
      </ol>
    </div>

    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',

  data: function() {
    return {
      title: 'Slot',
      message: 'This is message.',
    }
  },
}
</script>
