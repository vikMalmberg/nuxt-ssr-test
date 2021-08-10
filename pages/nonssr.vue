<template>
  <client-only>
    <div>
      <p>{{ posts }}</p>
      <h1>hello im nonssr</h1>
    </div>
  </client-only>
</template>

<script>
export default {
  data() {
    return {
      posts: []
    };
  },
  async created() {
    this.posts = await fetch("https://api.nuxtjs.dev/posts").then(res =>
      res.json()
    );
  }
};
</script>
