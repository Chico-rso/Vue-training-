<template>
  <div>
    <form @submit.prevent>
      <h4>Создание поста</h4>
      <input
        v-model="post.title"
        class="input"
        type="text"
        placeholder="Название"
      />
      <input
        v-model="post.body"
        class="input"
        type="text"
        placeholder="Описание"
      />
      <my-button @click="createPost">Создать</my-button>
    </form>
  </div>
</template>

<script>
import MyButton from "./UI/myButton.vue";
export default {
  components:{MyButton},
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