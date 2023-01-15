<template>
  <v-card
  color="dark.accent"
  width="300"
  class="mx-auto"
>
  <form @submit="onSubmit">
    <v-btn>Confirm</v-btn>
      <v-btn text @click="$emit('close')">Close</v-btn>
  </form>
</v-card>
</template>
<script>
export default {
  methods: {
    onSubmit() {
      console.log("first")
    }

  }
}
</script>