<template>
  <v-card class="mx-auto my-12" max-width="600">
    <v-img height="200" :src="imgUrl || 'https://cdn.vuetifyjs.com/images/cards/cooking.png'" :alt="title"></v-img>
  
    <v-card-title>{{ title }}</v-card-title>
  
    <v-card-text>
      <v-row align="center" class="mx-0">
        <v-rating :value="rating" color="amber" dense half-increments readonly size="14"></v-rating>
  
        <div class="grey--text ms-4">
          {{ rating }} (413)
        </div>
      </v-row>
  
      <div class="my-4 text-subtitle-1">
        {{ desc }}
      </div>
  
      <div>{{ text }}</div>
    </v-card-text>
  
    <v-divider class="mx-4"></v-divider>
  
    <v-card-actions>
      <nuxt-link :to="'/posts/' + 1">
        View details
      </nuxt-link>
    </v-card-actions>
  </v-card>
</template>
<script>
export default {
  props: {
    id: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    text: {
      type: String,
      required: true
    },
    desc: {
      type: String,
      required: true
    },
    imgUrl: {
      type: String,
      required: false,
    },
    rating: {
      type: Number,
      required: true
    },
  }
}
</script>