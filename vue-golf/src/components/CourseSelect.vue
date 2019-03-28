<template>
    <div>
        <h1>Course Select</h1>
        <select v-model="course">
            <option v-for="acourse in courses" v-bind:key="acourse.id" v-bind:value="acourse.id">{{acourse.name}}</option>
        </select>
        <button v-on:click="goToCourse">GO</button>
    </div>
</template>

<script>

    import axios from 'axios';

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
            }
        },
        methods: {
            goToCourse(){
                console.log(this.course);
            }
        },
    }
</script>

<style scoped>

</style>
