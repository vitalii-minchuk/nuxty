<template>
  <div>
    <h2>post: {{ $route.params.id }}</h2>
      <v-dialog transition="dialog-top-transition" v-model="addPostDialog">
        <template v-slot:activator="{ on, attrs }">
          <v-btn v-bind="attrs" v-on="on" @click="openAddPostDialog">
            Edit post
          </v-btn>
        </template>
        <AddPostForm @close="closeAddPostDialog" @create="addNewPost" />
      </v-dialog>
  </div>
</template>
<script>
import AddPostForm from '@/components/posts/AddPostForm.vue';

export default {
  components: { AddPostForm },
  data() {
    return {
      addPostDialog: false,
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