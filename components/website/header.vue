<template>
<div class="container-fluid p-0">
    <div class="d-flex bd-bottom bg-white justify-content-between pl-3 pr-3">
        <div class="align-self-center">
            <button class="btn pt-4 pb-4 ls-2"><b>UniversalSatellite</b></button>
        </div>
        <div class="text-right header-right">
            <div class="lg-screen">
                <button class="btn btn-hov pt-4 pb-4 pl-2 pr-2" v-for="(item, i) in links" :key="i" v-html="item"></button>
                <button @click="signup_or_signin($event)" class="btn btn-primary ml-4 pl-4 pr-4 box-shadow dropdown-btn">Account</button>
            </div>
            <button @click="open_menu($event)" class="btn btn-hov menu d-none material-icons dropdown-btn p-4">menu</button>
        </div>
    </div>
</div>
</template>

<script>
import dropdown_list from './dropdown-list.vue'
import vue from 'vue'
import $ from 'jquery'
export default {
    components: {
        dropdown_list
    },
    data() {
        return {
            visible: true,
            links: ["Biss 2020", "PowerVu 2020", "Receiver Software", "Satellite keys", "Channel TP"],
            register: ["Login", "Create Account"]
        }
    },
    methods: {
        open_menu(e) {
            let { html, instance } = this.component(dropdown_list, { e, list: this.links, width: 250 } )
            document.body.append(html)
        },
        signup_or_signin(e) {
            let { html, instance } = this.component(dropdown_list, { e, list: this.register, width:175 } )
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

}
</script>

<style>
@media only screen and (max-width: 1020px) {
  .header-right .lg-screen {
    display: none;
  }
  .header-right .menu {
      display: inline-block !important;
  }
}
</style>