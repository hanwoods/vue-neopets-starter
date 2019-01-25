<template>
    <div>
        <ImgComponent v-bind:file_name="pet_name"></ImgComponent>
        <div class="feed_block">
            <div>Feed your neopet!</div>
            <button> + </button>
            <div class="divider"/>
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
            }
        },
        components: {
            ImgComponent
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
}

.divider{
    width:5px;
    height:auto;
    display:inline-block;
}
</style>

