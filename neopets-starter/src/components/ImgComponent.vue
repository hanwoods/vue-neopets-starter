<template>
    <!-- notice how we use v-bind here instead of just id="{{file_name}}", mustaches cannot be used inside of HTML attributes -->
    <div class="inline-img" v-bind:id="file_name">
        <!-- here we have to wrap the image url in a require, beacuse assests are not served in development mode -->
        <img v-bind:alt="file_name" v-bind:ref="img_id" :src="require('../assets/'+file_name+'.png')" v-bind:style="{ height: img_size + 'px'}">
    </div>
</template>

<script>
    export default {
        name:"ImgComponent",
        props: {
            file_name: String,
            img_id: {
                type: Number,
                required: true
            },
            img_size: {
                type: Number,
                required: true
            }
        },
    }
    
</script>

<style>
    .inline-img {
        display: inline-block;
        max-width: 500px;
        max-height: 500px;
        margin: 0 2.5%;
    }
</style>

