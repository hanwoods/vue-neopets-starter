<template>
    <!-- notice how we use v-bind here instead of just id="{{file_name}}", mustaches cannot be used instead HTML attributes -->
    <div v-bind:id="file_name">
        <img v-bind:alt="file_name" :src="getImgUrl(file_name)">
    </div>
</template>

<script>
    function getImgUrl(file_name) {
        return '../assets/'+file_name+'.png';
    }
    export default {
        name:"Pet",
        props: {
            file_name: String
        }
    }
</script>
