<template>
<div class="container-fluid p-0">
    <search-engine />
    <search-content :category="category"/>
</div>
</template>

<script>
import search_engine from '@/components/home/search-engine.vue'
import search_content from '@/components/home/search-content.vue'
export default {
    components: {
        "search-engine": search_engine,
        "search-content": search_content,
    },
    data() {
        return {
            head: {
                title: 'UniversalSat - ' + this.$route.params.id,
                content: 'All the content will goes here. This is usefull of SEO optimization'
            },
            category: this.$route.params.id
        }
    },
    head () {
        return {
            title: this.head.title,
            meta: [
                // hid is used as unique identifier. Do not use `vmid` for it as it will not work
                { hid: 'description', name: 'description', content: this.head.content }
            ]
        }
    },    
    methods: {
    },
    mounted() {
    }
}
</script>

<style>

</style>