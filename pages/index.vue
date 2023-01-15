<template>
  <v-row justify="center" align="center">
    <div class="box">
      <h2>home page</h2>
    </div>
  </v-row>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style>
.box {
  width: 100%;
  height: calc(100vh - 56px);
  object-fit: cover;
  background-position: center;
  background-image: url(~assets/images/main-page-bg.jpg);
}
</style>
