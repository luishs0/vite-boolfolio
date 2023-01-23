<script>
export default {
    name: 'ProjectCard',
    data() {
        return {
            baseUrl: 'http://127.0.0.1:8000',
        }
    },
    props: {
        project: Object,
    }
}
</script>


<template>



    <div class="col-12 col-lg-6">
        <div class="card ms_card">
            <img v-if="project.cover_image" class="card-img-top ms_card-img"
                :src="`${baseUrl}/storage/${project.cover_image}`" alt="">
            <div v-else class="text-center p-1">
                No img
            </div>
            <div class="card-body">
                <h5 class="card-title">{{ project.title }}</h5>
                <p class="card-text">{{ project.description }}</p>
                <router-link :to="{ name: 'single-project', params: { slug: project.slug } }"
                    class="btn btn-primary">Learn More</router-link>
            </div>
        </div>
    </div>


</template>


<style lang="scss">
.ms_card-img {
    width: 100%;
    height: 10rem;
    object-fit: cover;
}
</style>
