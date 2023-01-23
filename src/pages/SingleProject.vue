<script>
import axios from 'axios';

export default {
    name: "SingleProject",
    data() {
        return {
            baseUrl: 'http://127.0.0.1:8000',
            project: {}
        }
    },
    created() {
        const slug = this.$route.params.slug;
        axios.get(`${this.baseUrl}/api/projects/${slug}`).then(resp => {
            if (resp.data.success) {
                this.project = resp.data.project;
            } else {
                this.$router.push({ name: "not-found" });
            }
        });
    },
}
</script>

<template>
    <main>
        <div class="container text-center">
            <h1> {{ project.title }}</h1>
            <img v-if="project.cover_image" class="w-50" :src="`${this.baseUrl}/storage/${project.cover_image}`" alt="">
            <div v-else class="pt-3 pb-3">
                No img
            </div>
            <p>{{ project.description }}</p>
        </div>
    </main>
</template>