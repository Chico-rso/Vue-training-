<template>
  <div>
    <form @submit.prevent>
      <h4>Создание поста</h4>
      <input
        v-bind:value="title"
				@input="title = $event.target.value"
        class="input"
        type="text"
        placeholder="Название"
      />
      <input
        v-bind:value="body"
				@input="body = $event.target.value"
        class="input"
        type="text"
        placeholder="Описание"
      />
      <button @click="createPost">Создать</button>
      <button @click="removePost">Удалить</button>
    </form>
    <div class="post" v-for="post in posts">
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong> {{ post.body }}</div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      posts: [
        { id: "1", title: "Js", body: "Description post" },
        { id: "2", title: "Html", body: "Description post" },
        { id: "3", title: "Css", body: "Description post" },
      ],
      title: "",
      body: "",
    };
  },
  methods: {
    createPost(){
			const newPost =
			{
				id: Date.now(),
				title: this.title,
				body: this.body
			}
			this.posts.push(newPost);
      this.title = "";
      this.body = "";

		},
		removePost()
		{
			this.posts.pop(this.newPost);
		}
  },
};
</script>
<style lang="css">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.post {
  padding: 15px;
  margin-bottom: 10px;
  border: 2px solid teal;
}
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
