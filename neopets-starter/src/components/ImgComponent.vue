<template>
    <!-- notice how we use v-bind here instead of just id="{{file_name}}", mustaches cannot be used inside of HTML attributes -->
    <div class="inline-img" v-bind:id="file_name">
        <!-- here we have to wrap the image url in a require, beacuse assests are not served in development mode -->
        <img v-bind:alt="file_name" :src="require('../assets/'+file_name+'.png')">
    </div>
</template>

<script>
    export default {
        name:"ImgComponent",
        props: {
            file_name: String
        }
    }
</script>

<style>
    .inline-img {
        display: inline-block;
        max-width: 200px;
        max-height: 200px;
        margin: 0 2.5%;
    }
</style>

