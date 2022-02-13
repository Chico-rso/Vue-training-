<template>
    <input :value="modelValue" @input="updateInput"  class="input" type="text">
</template>

<script>
  export default {
    name: 'my-input',
    props:{
      modelValue: [String, Number]
    },
    methods: {
      updateInput(event){
        this.$emit('update:modelValue', event.target.value)
      }
    },
  }
</script>

<style scoped>
  input {
  width: 90%;
  height: 40px;
  border: 1px solid teal;
  margin-top: 10px;
  margin-bottom: 10px;
  margin-left: 10px;
  margin-right: 10px;
  padding: 10px;
}
input:focus-visible {
  border: 1px solid rgb(245, 67, 13);
}
input:focus {
  border: 1px solid rgb(245, 67, 13);
}
</style>