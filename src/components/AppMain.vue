<script>

import axios from 'axios';
import ProjectCard from './ProjectCard.vue';

export default {
    name: 'AppMain',
    components: {
        ProjectCard
    },
    data() {
        return {
            baseUrl: 'http://127.0.0.1:8000',
            projects: [],
            loading: false
        }
    },
    created() {
        this.getProjects();
    },
    methods: {
        getProjects() {
            axios.get(`${this.baseUrl}/api/projects`).then(resp => { this.projects = resp.data.results; console.log(this.projects); })
        },
    },

}
</script>


<template>

    <h1 class="py-3">Projects</h1>

    <div class="row g-3">
        <ProjectCard :project="project" v-for="project in this.projects" :key="project.id" />
    </div>

</template>


<style lang="scss">

</style>