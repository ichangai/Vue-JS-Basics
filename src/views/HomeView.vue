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
import { ref } from 'vue'

export default {
    name: 'HomeView',
    components: { PostList },
    setup() {
        const posts = ref() 
        const error = ref(null)

        const load = async () => {
          try{
            let data  = await fetch('http://localhost:3000/posts')
            // console.log(data)
            if(!data.ok){
              throw Error('no data available')
            }
            posts.value = await data.json()

          }
          catch(err){
            error.value = err.message
            console.log(error.value)
          }
        }

        load()
        return { posts, error }
    },
}
</script>
