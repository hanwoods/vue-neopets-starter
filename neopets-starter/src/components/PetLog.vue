<template>
    <div class="logs">
        Food Diary for {{name}}:
        <ul id="pet_log">
            <li v-for="log in logs" v-bind:key="log.id"> {{log.message}} </li>
        </ul>
    </div>
</template>

<script>
export default {
    props: {
        logs: {
            type: Array,
            required: true
        },
        name: {
            type: String,
            required: true
        }
    }
}
</script>
