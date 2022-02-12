<template>
  <button>
    <slot></slot>
  </button>
</template>

<script>
export default {};
</script>

<style lang="css" scoped>
button {
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