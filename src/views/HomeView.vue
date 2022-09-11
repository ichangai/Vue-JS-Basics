<template>
  <div class="home">
    <h1>Glorious Purpose</h1>
  </div>
</template>

<script>
// @ is an alias to /src
import { ref } from 'vue'

export default {
  name: 'HomeView',
  setup(){
    const posts = ref([
      {title: 'How AI is used in advertisement', body: 'Brandex is utilizing AI to advertise products and services', id: 1 },
      {title: 'How AI is used in Shopping', body: 'Supermarkets are now using automated checkout baskets', id: 2 },
    ])

    return {posts}
  }
}
</script>
