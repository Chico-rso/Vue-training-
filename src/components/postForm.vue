<template>
  <div>
    <form @submit.prevent>
      <h4>Создание поста</h4>
      <my-input
        v-model="post.title"
        placeholder="Название"
      />
      <my-input
        v-model="post.body"
        placeholder="Описание"
      />
      <my-button @click="createPost">Создать</my-button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
    removePost() {
      this.$emit("remove", this.post);
    },
  },
};
</script>

<style  scoped>
form {
  display: flex;
  flex-direction: column;
}
button {
  display: inline-block;
  align-self: start;
  margin-bottom: 10px;
  margin-left: 10px;
  padding: 10px;
  line-height: 10px;
  background-color: aquamarine;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}
</style>