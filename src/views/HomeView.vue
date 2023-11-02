<template>
  <div class="home">
    <h1>Home</h1>
    <PostList :posts="posts" />
  </div>
</template>

<script>
import PostList from '@/components/PostList.vue'
import { ref } from 'vue'

export default {
  name: 'HomeView',
  components: { PostList },
  setup() {
    const posts = ref([
      { title: 'Welcome to the blog', body: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum voluptate asperiores delectus quae nam natus cupiditate rem quis facere necessitatibus quidem, laudantium molestiae, dolores at, sapiente aspernatur! Doloribus, neque et!', id: 1 },
      { title: 'Top 5 CSS tips', body: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Laborum omnis quod doloribus, animi molestiae voluptates recusandae, quidem eligendi odio expedita eaque. Fugit dolorum quibusdam earum illo, ipsum placeat eveniet officiis.', id: 2 }
    ])
    
    return { posts }
  },
}
</script>