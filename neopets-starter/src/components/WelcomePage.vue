<template>
  <div class="welcome_page">
    
    <div>
      <h1>{{ header_msg }}</h1>
    </div>

    <div>
      <PetPage v-if="selected_neopet" v-bind:pet_name="selected_neopet.name" v-bind:pet_id="selected_neopet.id"></PetPage>
      <template v-else>
        <h2>{{ sub_msg }}</h2>
        <div id="neopets">
          <!-- Note in v-for you need a key to bind to each element and we use v-bind to pass in the image.url -->
          <ImgComponent v-for="pet in pets" v-bind:file_name="pet.name" v-bind:img_id="pet.id" :key="pet.id" v-on:click.native="setSelectedNeopet(pet)"></ImgComponent>
        </div>
      </template>
    </div>

  </div>     
</template>

<script>
import ImgComponent from './ImgComponent.vue'
import PetPage from './PetPage.vue'

export default {
  name: 'WelcomePage',
  props: {
    header_msg: {
      type: String,
      required: true
    },
    sub_msg:  {
      type: String,
      requred: false
    }
  },
  components: {
    ImgComponent,
    PetPage
  },
  data: function() {
    return {
      pets: [
        { name: "acara", id: 1 },
        { name: "aisha", id: 2 },
        { name: "lenny", id: 3 },
        { name: "kau", id: 4 },
      ],
      selected_neopet: ""
    }
  },
  methods: {
    setSelectedNeopet(pet) {
      this.selected_neopet = pet;
    }
  }
}
</script>