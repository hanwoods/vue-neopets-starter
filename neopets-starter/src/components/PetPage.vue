<template>
    <div>
        <ImgComponent v-bind:file_name="pet_name" v-bind:img_size="current_size" v-bind:img_id="pet_id"></ImgComponent>
        <div class="feed_block">
            <div>Feed your neopet!</div>
            <button> + </button>
            <button> - </button>
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
            }
        },
        components: {
            ImgComponent
        },
        data: function() {
            return {
                current_size: 1
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

