<template>
<div>
	<div class="post" v-for="post in posts">
		{{ post.title }}
		{{ post.body }}
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
				{ id: "3", title: "Css", body: "Description post" }
			],
		}
	},
	methods: {},
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
</style>
