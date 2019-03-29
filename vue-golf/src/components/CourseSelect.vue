<template>
    <div>
        <h1>Course Select</h1>
        <select v-model="course">
            <option v-for="acourse in courses" v-bind:key="acourse.id" v-bind:value="acourse.id">{{acourse.name}}</option>
        </select>
        <button v-on:click="goToCourse">GO</button>
        <h3 v-if="warning.show">{{warning.text}}</h3>
    </div>
</template>

<script>

    import axios from 'axios';
    // import Router from '../Router';

    export default {
        name: "CourseSelect",
        created(){
            axios.get('https://golf-courses-api.herokuapp.com/courses')
                .then(response => {
                    console.log(response.data.courses);
                    this.courses = response.data.courses;
                });
        },
        data(){
            return {
                courses: [],
                course: '',
                warning: {show: false, text: ''},
            }
        },
        methods: {
            goToCourse(){
                console.log(this.course);
                if(this.course){
                    this.$router.push({ name: 'Course', params: { courseId: this.course }});
                }
                else{
                    this.warning = {show: true, text: 'You must choose a course to continue!'};
                }
            }
        },
        components: {
            // Router,
        },
        computed: {

        }
    }
</script>

<style scoped>

</style>
