<template>
  <header>
      <h2>Latest Posts</h2>
      <ul>
          <li v-for="post in posts" key="post.id">
              <h3>{{post.title}}</h3>
          </li>
      </ul>
  </header>
</template>

<script>
export default {
    name: "Main",
    data() {
        return {
            posts: []
        }
    },
    created(){
        axios.get("/api/posts")
            .then((response)=> {
                this.posts = response.data;
            })
    }
}
</script>

<style lang="scss" scoped>

</style>