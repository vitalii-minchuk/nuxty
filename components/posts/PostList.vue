<template>
  <v-col>
    <PostDetails
      v-for="post in posts"
      :key="post.id"
      :id="post.id"
      :title="post.title"
      :text="post.text"
      :desc="post.desc"
      :imgUrl="post.imgUrl"
      :rating="post.rating"
    />
  </v-col>
</template>
<script>
import PostDetails from './PostDetails.vue';

export default {
    components: { PostDetails },
    data() {
      return {
        posts: [
          {
            id: '1',
            title: 'Cafe Badilico',
            text: 'Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.',
            rating: 4,
            desc: '$ • Italian, Cafe',
            imgUrl: 'https://cdn.vuetifyjs.com/images/cards/cooking.png'
          },
          {
            id: '2',
            title: 'Cafe Leonardo',
            text: 'Salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.',
            rating: 5,
            desc: '$ • Italian, Cafe',
            imgUrl: 'https://cdn.vuetifyjs.com/images/cards/cooking.png'
          },
        ]
      }
    }
}
</script>