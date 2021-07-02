<template>
  <div class=" tw-items-center tw-justify-center tw-bg-gray-500 tw-h-screen tw-w-screen tw-flex tw-flex-col">
    <button class="tw-rounded-lg tw-bg-indigo-600 tw-text-white tw-px-4 tw-py-3 tw-font-semibold tw-text-lg tw-leading-tight tw-shadow-md hover:tw-bg-indigo-700 ">
      Show Sliding Verification
    </button>
    <div ref="placeholder" class="tw-h-10"></div>
    <SlidingVerification/>
    <div ref="footer-placeholder" class="tw-h-40"></div>
  </div>
</template>

<script>
import SlidingVerification from './SlidingVerification.vue'
  export default {
    name: 'HelloWorld',
    components:{
      SlidingVerification,
    },
    data: () => ({
    }),
    created(){
      this.$utils.dynamic_append_link("https://cdn.jsdelivr.net/npm/animate.css@4.1.1/animate.min.css")
    },
    mounted(){
    },
    watch:{
    },
    computed:{
    },
    methods:{
    }
  }
</script>


<style scoped lang="scss">
</style>