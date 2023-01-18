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
import PostDetails from '@/components/posts/PostDetails.vue';

export default {
    components: { PostDetails },
    props: ['posts']
}
</script>