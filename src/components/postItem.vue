<template>
  <div class="post">
    <div>
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong> {{ post.body }}</div>
    </div>
    <div class="post__btns">
      <my-button @click="$emit('remove', post)">Удалить</my-button>
      <my-button @click="editPost">Изменить</my-button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
  methods: {},
};
</script>

<style lang="css" scoped>
.post {
  display: flex;
  align-items: center;
  max-width: 100%;
  width: 1000px;
  justify-content: space-between;
  padding: 15px;
  margin-bottom: 10px;
  border: 2px solid teal;
}
</style>