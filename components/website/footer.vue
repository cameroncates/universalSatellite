<template>
<div class="container-fluid bg-white p-3 border">
    <p class="w-75 m-auto">&copy; {{year}} UniversalSatellite. All Rights Reserved.</p>
</div>
</template>

<script>
export default {
    data() {
        return {
            year: null
        }
    },
    mounted() {
        this.year = new Date().getFullYear()
    }

}
</script>

<style>

</style>