<template>
   <div class="welcome_page">
    <h1>{{ header_msg }}</h1>
    <h2>{{ sub_msg }}</h2>
    <Pet file_name="jubjub_pet"></Pet>
    </div>     
</template>

<script>
import Pet from './Pet.vue'

export default {
  name: 'WelcomePage',
  props: {
    header_msg: String,
    sub_msg: String
  },
  components: {
    Pet
  }
}
</script>