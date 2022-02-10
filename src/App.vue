<template>
  <div class="app">
    <post-form />
    <post-list :posts="posts"/>
  </div>
</template>
<script>
import PostForm from "@/components/postForm";
import PostList from "@/components/postList";
export default {
  components:{
    PostForm, PostList
  },
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

</style>
