<template>
  <div class="home">
    <h1>Glorious Purpose</h1>

    <div v-if="error">
      <h3>Error Loading Data.....<br/> Try again later</h3>
    </div>

    <div class="" v-if="posts.length">
      <PostList :posts="posts"/>
    </div>

    <div class="" v-else>
      <img src="@/assets/Ripple.gif" alt="">
    </div>

  </div>
</template>

<script>
// @ is an alias to /src
import PostList from '@/components/PostList.vue'
import getPosts from '@/composables/getPosts'

export default {
    name: 'HomeView',
    components: { PostList },
    setup() {
    const {posts, error, load} = getPosts()
    load()
    return { posts, error } 
    },
}
</script>
