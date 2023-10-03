<template>
  <div v-for="post of posts" :key="post.id">
    <Post
        v-bind:post="post"
    />
  </div>
</template>

<script>
import Post from "@/components/PostItem.vue";

export default {
  components: {Post},
  data() {
    return {
      posts: [],
    }
  },
  methods: {
    fetchPosts() {
      fetch('https://jsonplaceholder.typicode.com/posts?_page=2&_limit=2')
          .then(async res => {
            this.posts = await res.json()
          })
          .catch((reason) => console.log(reason))
    },
  },
  created() {
    this.fetchPosts();
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  height: 100%;
}

body {
  min-height: 100%;
  background: #37393A;
}

</style>