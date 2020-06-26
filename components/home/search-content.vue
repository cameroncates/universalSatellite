<template>
<div class="container-fluid p-4">
    <h5 class="w-100 search-category-title">{{category.replace("-", " ")}}</h5>

    <div class="container-fluid d-flex flex-wrap justify-content-center">
        <div class="box-shadow bg-white m-4 search-content-card align-self-end" v-for="(item, i) in content" :key="i">
            <div :style="style.img" class="mb-3">
                <img :src="item.thumbnail" width="100%" alt="">
            </div>
            <div class="p-3">
                <div class="w-100 d-flex justify-content-between mb-3">
                    <p class="font-weight-bold small d-flex align-items-center"><span class="material-icons mr-2 text-primary">access_time</span> {{item.date}}</p>
                    <p class="font-weight-bold small d-flex align-items-center">
                        <span class="material-icons mr-1">comment</span> {{item.comments}}
                        <span class="ml-3 mr-3"></span>
                        <span class="material-icons mr-1 text-danger">local_fire_department</span> {{item.downloads}}
                    </p>
                </div>
                <h5 v-html="item.title"></h5>
                <p>
                    <span>{{item.description.substr(0, item.limit)}} {{item.limit == 200 ? '...' : '' }}</span>
                    <span v-if="item.limit == 200" @click="[item.limit = item.description.length]" class="text-primary text-sm btn p-1 btn-hov">show more</span>
                </p>
            </div>
        </div>         
    </div>

</div>
</template>

<script>
import img1 from '@/assets/images/1.jpg'
import img2 from '@/assets/images/2.jpg'
import img3 from '@/assets/images/3.jpg'
export default {
    props: {
        category: {
            required: true
        },
        keywords: {
            required: false
        }
    },
    data() {
        return {
            style: {
                img: {
                    width: '100%',
                    maxHeight: '400px',
                    overflow: 'hidden'
                }
            },
            content: [
                { title: "Star Movie HD New Frequency 2020", description: "star movies frequency nss6, star movies frequency and symbol rate, star movies frequency philippines, star movies frequency hotbird, star movies action frequency, star movies hd frequency, star movies india frequency, star movies frequency tanzania, star movies action frequency", 
                date: " 3 weeks ago", thumbnail: img1, comments: 250, downloads: '5,301', limit: 200 },
                { title: "Star Movie HD New Frequency 2020", description: "star movies frequency nss6, star movies frequency and symbol rate, star movies frequency philippines, star movies frequency hotbird, star movies action frequency, star movies hd frequency, star movies india frequency, star movies frequency tanzania, star movies action frequency", 
                date: " 3 weeks ago", thumbnail: img2, comments: 250, downloads: '5,301', limit: 200 },
                { title: "Star Movie HD New Frequency 2020", description: "star movies frequency nss6, star movies frequency and symbol rate, star movies frequency philippines, star movies frequency hotbird, star movies action frequency, star movies hd frequency, star movies india frequency, star movies frequency tanzania, star movies action frequency", 
                date: " 3 weeks ago", thumbnail: img3, comments: 250, downloads: '5,301', limit: 200 },
                { title: "Star Movie HD New Frequency 2020", description: "star movies frequency nss6, star movies frequency and symbol rate, star movies frequency philippines, star movies frequency hotbird, star movies action frequency, star movies hd frequency, star movies india frequency, star movies frequency tanzania, star movies action frequency", 
                date: " 3 weeks ago", thumbnail: img2, comments: 250, downloads: '5,301', limit: 200 },
                { title: "Star Movie HD New Frequency 2020", description: "star movies frequency nss6, star movies frequency and symbol rate, star movies frequency philippines, star movies frequency hotbird, star movies action frequency, star movies hd frequency, star movies india frequency, star movies frequency tanzania, star movies action frequency", 
                date: " 3 weeks ago", thumbnail: img3, comments: 250, downloads: '5,301', limit: 200 },
                { title: "Star Movie HD New Frequency 2020", description: "star movies frequency nss6, star movies frequency and symbol rate, star movies frequency philippines, star movies frequency hotbird, star movies action frequency, star movies hd frequency, star movies india frequency, star movies frequency tanzania, star movies action frequency", 
                date: " 3 weeks ago", thumbnail: img1, comments: 250, downloads: '5,301', limit: 200 },
                { title: "Star Movie HD New Frequency 2020", description: "star movies frequency nss6, star movies frequency and symbol rate, star movies frequency philippines, star movies frequency hotbird, star movies action frequency, star movies hd frequency, star movies india frequency, star movies frequency tanzania, star movies action frequency", 
                date: " 3 weeks ago", thumbnail: img2, comments: 250, downloads: '5,301', limit: 200 },
            ]
        }
    },
    mounted() {
    }
}
</script>

<style>
.search-content-card {
    width: 525px;
}
@media only screen and (max-width: 800px) {
    .search-content-card {
        width: 100% !important;
    } 
}
@media only screen and (max-width: 1250px) {
    .search-content-card {
        width: 100% !important;
    } 
}
</style>