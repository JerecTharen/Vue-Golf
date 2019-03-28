<template>
    
</template>

<script>
    import Vue from 'vue'
    import Router from 'vue-router'
    import CourseSelect from './components/CourseSelect';
    import Course from './components/Course';

    Vue.use(Router);

    export default new Router({
        routes: [
            {
                path: '/',
                name: 'CourseSelect',
                component: CourseSelect,
            },
            {
                path: '/course/:courseId',
                name: 'Course',
                component: Course,
            }
        ]
    });
</script>

<style scoped>

</style>
