<template>
 <div>
    <v-row>
      <v-text-field v-model="userId" label="User ID"></v-text-field>
      <v-btn @click="addUser">add user</v-btn>
    </v-row>
    <NuxtChild />
 </div>
</template>
<script>
export default {
  layout: 'users',
  data() {
    return {
      userId: ''
    }
  },
  methods: {
    addUser() {
      this.$router.push(`/users/${this.userId}`)
    }
  },
}
</script>