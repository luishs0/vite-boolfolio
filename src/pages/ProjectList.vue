<script>

import axios from 'axios';
import ProjectCard from '../components/ProjectCard.vue';

export default {
    name: 'AppMain',
    components: {
        ProjectCard
    },
    data() {
        return {
            baseUrl: 'http://127.0.0.1:8000',
            projects: [],
            loading: true
        }
    },
    created() {
        this.getProjects();
    },
    methods: {
        getProjects() {
            axios.get(`${this.baseUrl}/api/projects`).then(resp => { this.projects = resp.data.results; console.log(this.projects); this.loading = false; })
        },
    },

}
</script>


<template>
    <div class="container">
        <h1 class="py-3">Projects</h1>

        <h3 v-if="this.loading" class="text-center">Loading...</h3>
        <div class="row g-3">
            <ProjectCard :project="project" v-for="project in this.projects" :key="project.id" />
        </div>
    </div>

</template>


<style lang="scss">

</style>