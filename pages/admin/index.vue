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
      <AddPostForm @close="closeAddPostDialog" />
    </v-dialog>
    <v-divider class="mx-4 mt-8"></v-divider>
    <PostList />
  </div>
</template>
<script>
import AddPostForm from '../../components/posts/AddPostForm.vue';
import PostList from '../../components/posts/PostList.vue';

export default {
    components: { PostList, AddPostForm },
    data() {
      return {
        addPostDialog: false
      }
    },
    methods: {
      openAddPostDialog() {
        this.addPostDialog = true
      },
      closeAddPostDialog() {
        this.addPostDialog = false
      }
    }
}
</script>