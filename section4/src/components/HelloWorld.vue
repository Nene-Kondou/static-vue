<template>
  <div class="alert alert-primary">

    <!-- ① -->
    <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <hr>
    <p>Number: {{ num }}</p> 
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
    num: {
      type: Number,
      default: 100,
      validator: ( value ) => {
        // 3つの式が全部trueならtrue 整数で0以上100未満
        return value == parseInt( value ) && value >= 0 && value <= 100
      },
    }
  },
  data() {
    return {
      message: 'バリデーション・チェック',
    }
  }
}
</script>
