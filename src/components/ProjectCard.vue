<script>
export default {
    name: 'ProjectCard',
    props: {
        project: Object,
    }
}
</script>


<template>



    <div class="col-12 col-lg-6">
        <div class="card ms_card">
            <img src="..." class="card-img-top" alt="...">
            <div class="card-body">
                <h5 class="card-title">{{ project.title }}</h5>
                <p class="card-text">{{ project.description }}</p>
                <a href="#" class="btn btn-primary">Learn More</a>
            </div>
        </div>
    </div>


</template>


<style lang="scss">

</style>
