<template>
    <div>
        <!-- Notice here how you can use v-bind: or the short hand : to bind data or props to html atributes -->
        <ImgComponent v-bind:file_name="pet_name" :img_size="current_size" v-bind:img_id="pet_id"></ImgComponent>
        <div class="feed_block">
            <div>Feed your neopet!</div>
            <button v-on:click="feedPet()"> + </button>
            <button v-on:click="starvePet()"> - </button>
        </div>
    </div>
</template>

<script>
    import ImgComponent from './ImgComponent.vue'

    export default {
        name:"PetPage",
        props: {
            pet_name: {
                type: String,
                required: true
            },
            pet_id: {
                type: Number,
                required: true
            },
            pet_height: {
                type: Number,
                required: true
            }
        },
        components: {
            ImgComponent
        },
        data: function () {
            return {
                current_size: 250
            }
        },
        methods : {
            feedPet: function() {
                this.current_size += 20;
            },
            starvePet: function() {
                this.current_size -= 20;
            }
        }
    }
</script>

<style>
.feed_block {
    display: inline-block;
    vertical-align: top;
    padding-top: 100px;
}

button {
    display:inline-block;
    margin-left: 10px;
}
</style>

