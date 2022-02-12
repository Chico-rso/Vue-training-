<template>
  <div class="app">
    <post-form @create="createPost" />
    <post-list :posts="posts" @remove="removePost"/>
  </div>
</template>
<script>
import PostForm from "@/components/postForm";
import PostList from "@/components/postList";
export default {
  components: {
    PostForm,
    PostList,
  },
  data() {
    return {
      posts: [
        { id: "1", title: "Js", body: "Description post" },
        { id: "2", title: "Html", body: "Description post" },
        { id: "3", title: "Css", body: "Description post" },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
  },
};
</script>
<style lang="css">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
