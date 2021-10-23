<template>
  <div class="mx-24">
    <h1>Blog</h1>
    <div class="">
      <div class="card" v-for="post in posts" :key="post.id">
        <router-link :to="'/blog/' + post.slug">{{ post.title }}</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Blog",
  data() {
    return {
      posts: this.fetchPosts(),
      loading: true,
      error: null,
    };
  },
  created() {},
  methods: {
    // Fetch the blog posts from the API using fetch().
    // The data is then stored in the posts array.
    fetchPosts() {
      fetch("https://jsonplaceholder.typicode.com/posts")
        .then((response) => response.json())
        .then((json) => {
          this.posts = json;
          this.loading = false;
        })
        .catch((error) => {
          this.error = error;
          this.loading = false;
        });
    },
    createPost() {
      // Create a new post using the API.
      // The new post is then stored in the posts array.
      fetch("https://jsonplaceholder.typicode.com/posts", {
        method: "POST",
        body: JSON.stringify({
          title: "New Post",
          body: "New Post Body",
          userId: 1,
        }),
      })
        .then((response) => response.json())
        .then((json) => {
          this.posts.push(json);
        })
        .catch((error) => {
          this.error = error;
        });
    },

    deletePost() {
      // Delete the last post in the posts array.
      // The deleted post is then removed from the posts array.
      fetch("https://jsonplaceholder.typicode.com/posts/" + this.posts[0].id, {
        method: "DELETE",
      })
        .then((response) => response.json())
        .then((json) => {
          this.posts.splice(0, 1);
        })
        .catch((error) => {
          this.error = error;
        });
    },

    updatePost() {
      // Update the first post in the posts array.
      // The updated post is then stored in the posts array.
      fetch("https://jsonplaceholder.typicode.com/posts/" + this.posts[0].id, {
        method: "PUT",
        body: JSON.stringify({
          title: "Updated Post",
          body: "Updated Post Body",
          userId: 1,
        }),
      })
        .then((response) => response.json())
        .then((json) => {
          this.posts[0] = json;
        })
        .catch((error) => {
          this.error = error;
        });
    },
  },
};
</script>

<style scoped>
.card {
  border-radius: 4px;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2);
  padding: 24px;
  /* make the card clickable */
  cursor: pointer;
}
</style>
