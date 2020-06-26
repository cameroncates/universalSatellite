<template>
<div class="container-fluid d-flex align-items-center w-100 bg-white bd-bottom flex-wrap" :style="style.container">
    <div class="input-group w-75 m-auto search-container border bg-light box-shadow p-1">
        <div class="input-group-prepend">
            <span class="input-group-text material-icons bg-none bd-none">search</span>
        </div>
        <input type="text" class="form-control bd-none bg-none" placeholder="Search for">
        <div class="input-group-append">
            <span @click="search_category($event)" class="input-group-text bd-none btn material-icons bg-none btn-hov dropdown-btn">arrow_drop_down</span>
        </div>
    </div>    

</div>
</template>

<script>
import $ from 'jquery'
import vue from 'vue'
import dropdown_list from '@/components/website/dropdown-list.vue'
export default {
    data() {
        return {
            style: {
                container : {
                    height: '500px'
                }
            },
            category: ["All", "Biss 2020", "PowerVu 2020", "Receiver Software", "Satellite keys", "Channel TP"],
        }
    },
    methods: {
        search_category(e) {
            let { html, instance } = this.component(dropdown_list, { e, list: this.category, width: 250, selected: this.$route.params.id } )
            instance.$on('select', payload => {
                this.$router.push('/category/'+payload.replace(" ", "-"))
            })
            document.body.append(html)

        },
        component(component, props = null) {
            let ComponentClass = vue.extend(component)
            let instance = new ComponentClass({ propsData: props })
            instance.$mount()
            return {
                html: instance.$el,
                instance
            }
        },        
    },
    mounted() {
        // this.style.container.height = ($(window).height() - 500) + 'px'
    }
}
</script>

<style>
.search-container {
    border-radius: 5px;
}
@media only screen and (max-width: 800px) {
  .search-container {
      width: 100% !important;
  }
}

</style>