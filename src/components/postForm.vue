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
        v-model="post.title"
        class="input"
        type="text"
        placeholder="Описание"
      />
      <button>Создать</button>
      <button>Удалить</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: ""
      }
    }
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