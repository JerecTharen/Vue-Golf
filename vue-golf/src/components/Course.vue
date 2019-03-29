<template>
    <div id="course">
        <h1>Course: {{courseInfo.name}}</h1>
        <ScoreTable :holes="holes" />
    </div>
</template>

<script>
    import ScoreTable from './ScoreTable';
    import axios from 'axios';

    export default {
        name: "Course",
        mounted(){
            axios.get(`https://golf-courses-api.herokuapp.com/courses/${this.$route.params.courseId}`)
                .then(response => {
                    this.courseInfo = response.data.data;
                    this.holes = this.courseInfo.holes;
                    console.log(this.courseInfo);
                });
        },
        data(){
            return {
                courseId: this.$route.params.courseId,
                courseInfo: {},
                holes: [],
            }
        },
        components: {
            ScoreTable,
        },
    }
</script>
<style scoped>

</style>
