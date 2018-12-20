<template>
   <div class="welcome_page">
    <h1>{{ header_msg }}</h1>
    <h2>{{ sub_msg }}</h2>
    </div>     
</template>

<script>
export default {
  name: 'WelcomePage',
  props: {
    header_msg: String,
    sub_msg: String
  }
}
</script>