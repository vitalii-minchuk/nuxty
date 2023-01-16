<template>
  <v-card
  color="dark.accent"
  width="300"
  class="mx-auto"
>
<v-text-field v-model="title" label="Title" required></v-text-field>
<v-text-field v-model="desc" label="Description" required></v-text-field>
<v-text-field v-model="text" label="Text" required></v-text-field>
<v-text-field v-model="rating" label="Rating"></v-text-field>
<v-text-field v-model="imgUrl" label="Image url"></v-text-field>
  <v-btn text @click="$emit('close')">Close</v-btn>
  <v-btn @click="onSave">Confirm</v-btn>
</v-card>
</template>
<script>

export default {
  data() {
    return {
      text: '',
      desc: '',
      rating: 4,
      title: '',
      imgUrl: ''
    }
  },
  emits: ['close', 'create'],
  methods: {
    onSave() {
      const post = {
        title: this.title,
        text: this.text,
        rating: +this.rating,
        desc: this.desc,
        imgUrl: this.imgUrl,
        id: new Date().toISOString()
      }
      this.$emit('create', post)
      this.$emit('close')
    }
  }
}
</script>