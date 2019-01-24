<template>
  <div class="welcome_page">
    <h1>{{ header_msg }}</h1>
    <h2>{{ sub_msg }}</h2>
    <div id="neopets">
      <!-- Note in v-for you need a key to bind to each element and we use v-bind to pass in the image.url -->
      <ImgComponent v-for="image in images" v-bind:file_name="image.url" :key="image.key"></ImgComponent>
    </div>
  </div>     
</template>

<script>
import ImgComponent from './ImgComponent.vue'

export default {
  name: 'WelcomePage',
  props: {
    header_msg: String,
    sub_msg: String
  },
  components: {
    ImgComponent
  },
  data: function() {
    return {
      images: [
        { url: "acara", id: "1" },
        { url: "aisha", id: "2" },
        { url: "lenny", id: "3" },
        { url: "kau", id: "4" },
      ]
    }
  }
}
</script>