<template>
<div class="container-fluid w-100 h-100">
  <button class="btn btn-block text-center p-4">
     <span class="spinner-border spinner-border-sm mb-2"></span>
     <br>
     <span>Please wait</span>
  </button>
</div>
</template>

<script>
export default {
  mounted() {
    setTimeout(() => {
      this.$router.push('/category/ChannelTP')    
    }, 250);
  }
}
</script>

<style>

</style>