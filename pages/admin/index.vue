<template>
  <div>
    <v-dialog
      transition="dialog-top-transition"
      v-model="addPostDialog"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn  v-bind="attrs" v-on="on" @click="openAddPostDialog">
          Add post
        </v-btn>
      </template>
      <AddPostForm @close="closeAddPostDialog" @create="addNewPost" />
    </v-dialog>
    <v-divider class="mx-4 mt-8"></v-divider>
    <PostList :posts="posts" />
  </div>
</template>
<script>
import AddPostForm from '../../components/posts/AddPostForm.vue';
import PostList from '../../components/posts/PostList.vue';

export default {
    components: { PostList, AddPostForm },
    data() {
      return {
        addPostDialog: false,
        posts: [
          {
            id: '1',
            title: 'Cafe Badilico',
            text: 'Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.',
            rating: 4,
            desc: '$ • Italian, Cafe',
            imgUrl: 'https://plus.unsplash.com/premium_photo-1661501114842-78d492e3acc9?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8N3x8Y2FmZSUyMGZvb2R8ZW58MHx8MHx8&auto=format&fit=crop&w=900&q=60'
          },
          {
            id: '2',
            title: 'Cafe Leonardo',
            text: 'Salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.',
            rating: 5,
            desc: '$ • Italian, Cafe',
            imgUrl: ''
          },
        ]
      }
    },
    methods: {
      openAddPostDialog() {
        this.addPostDialog = true
      },
      closeAddPostDialog() {
        this.addPostDialog = false
      },
      addNewPost(post) {
        this.posts = [post, ...this.posts]
      }
    }
}
</script>