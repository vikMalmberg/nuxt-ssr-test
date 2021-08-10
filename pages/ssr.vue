<template>
  <div>
    <p>{{ JSON.stringify(posts) }}</p>
    <h1>Hi im server rendered page</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: []
    };
  },
  head() {
    return {
      title: "SSR rendered title",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "My custom description"
        }
      ]
    };
  },
  async fetch() {
    this.posts = await fetch("https://api.nuxtjs.dev/posts").then(res =>
      res.json()
    );
  }
};
</script>
