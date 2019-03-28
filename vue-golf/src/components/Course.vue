<template>
    <h1>Course: {{courseId}}</h1>
</template>

<script>
    export default {
        name: "Course",
        data(){
            return {
                courseId: this.props.params.courseId,
            }
        },
    }
</script>
<style scoped>

</style>
