<!-- @format -->

<template>
  <div class="item">
    <dl>
      <dt>{{ title }}
        <span style="float: right">更多</span>
    </dt>
      <slot name="main"></slot>
    </dl>
  </div>
</template>

<script>
export default {
  name: 'item',
  props: ['title']
};
</script>

<style lang="less" scoped>
.item {
  width: 386px;
  margin: 20px auto;
}

dl {
  width: 100%;
  margin: 0 auto;
  background-color: #fff;
  outline: 1px solid #ccc;

  dt {
    outline: 1px solid #ccc;
    padding: 10px;
  }
}




</style>
