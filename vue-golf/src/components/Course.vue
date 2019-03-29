<template>
    <h1>Course: {{$route.params.courseId}}</h1>
</template>

<script>
    export default {
        name: "Course",
        data(){
            return {
                courseId: this.$route.params.courseId,
            }
        },
        props: {
            // courseId: Number,
        },
    }
</script>
<style scoped>

</style>
