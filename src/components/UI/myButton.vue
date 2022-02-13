<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button'
};
</script>

<style lang="css" scoped>
.btn{
  display: inline-block;
  align-self: start;
  margin-right: 10px;
  padding: 10px;
  line-height: 10px;
  background-color: aquamarine;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}

</style>