<template>
<!--    <p>Hello: {{holeId}}</p>-->
    <div>
        <p v-for="hole in holes">{{hole.hole}}</p>
    </div>
</template>

<script>
    export default {
        name: "ScoreTable",
        props: [
            'holes',
        ],
        data(){
            return {

            }
        },
    }
</script>

<style scoped>

</style>
