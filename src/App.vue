<template>
  <div class="app">
    <h1>Страница с постами</h1>
    <my-button @click="showDialog">Создать пост</my-button>
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost" />
    </my-dialog>
    <post-list :posts="posts" @remove="removePost"/>
  </div>
</template>
<script>
import PostForm from "@/components/postForm";
import PostList from "@/components/postList";
export default {
  components: {
    PostForm,
    PostList

  },
  data() {
    return {
      posts: [
        { id: "1", title: "Js", body: "Description post" },
        { id: "2", title: "Html", body: "Description post" },
        { id: "3", title: "Css", body: "Description post" },
      ],
      dialogVisible: false,
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    },
    showDialog() {
      this.dialogVisible = true;
    }
  },
};
</script>
<style lang="css" scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
button{margin: 10px;}
</style>
