<template>
    <div>
        <!-- Notice here how you can use v-bind: or the short hand : to bind data or props to html atributes -->
        <ImgComponent v-bind:file_name="pet_name" :img_size="current_size" v-bind:img_id="pet_id"></ImgComponent>
        <div class="feed_block">
            <div>Feed your neopet!</div>
            <button v-on:click="feedPet()"> + </button>
            <button v-on:click="starvePet()"> - </button>
        </div>
        <PetLog v-bind:name="pet_name" v-bind:logs="logs"></PetLog>
    </div>
</template>

<script>
    import ImgComponent from './ImgComponent.vue'
    import PetLog from './PetLog.vue'

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
            ImgComponent,
            PetLog
        },
        data: function () {
            return {
                current_size: 250,
                logs: []
            }
        },
        methods : {
            feedPet: function() {
                this.logs.push({
                    id: this.logs.length,
                    message: "Pet fed!"
                });
                this.current_size += 20;
            },
            starvePet: function() {
                this.logs.push({
                    id: this.logs.length,
                    message: "Pet starved!"
                });
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

