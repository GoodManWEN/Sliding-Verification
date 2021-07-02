<template>
  <div class="tw-h-88 tw-w-88 tw-bg-gray-50 tw-rounded-md tw-p-4">
    <div class=" tw-text-gray-400 tw-text-sm  tw-select-none">安全验证</div>
    <div class=" tw-text-gray-900 siyuan-heiti tw-text-xl tw-mt-1  tw-select-none">拖动下方滑块完成拼图</div>
    <div class=" tw-mt-2 tw-select-none">
      <img class="tw-object-cover tw-w-full tw-rounded-sm" style="height:168px" src="https://img2.baidu.com/it/u=4064921610,597246006&fm=26&fmt=auto&gp=0.jpg">
    </div>
    <div ref="slider" class="tw-mt-1 tw-h-14 tw-overflow-hidden">
      <div ref="scrollbar" class="tw-w-full tw-h-4 tw-bg-gray-300 tw-rounded-lg tw-mt-5"></div>
      <div ref="box" class="tw-h-9 tw-w-16 tw-bg-blue-500 tw-relative tw-rounded-full tw-flex tw-flex-row tw-justify-center tw-items-center glow-effect" style="left:15px;top:-26px">
        <div class="tw-bg-gray-50 tw-w-0.5" style="height:14px"></div>
        <div style="width:7px"></div>
        <div class="tw-bg-gray-50 tw-w-0.5" style="height:14px"></div>
        <div style="width:7px"></div>
        <div class="tw-bg-gray-50 tw-w-0.5" style="height:14px"></div>
      </div>
    </div>
    <div ref="footer" class=" tw-w-full tw-h-8 tw-flex tw-flex-row-reverse  tw-items-center">
      <div class="tw-w-20 tw-flex tw-flex-row-reverse">
        <div class=" tw-h-8 tw-w-8 tw-rounded-full tw-border-gray-300 tw-flex tw-items-center tw-justify-center tw-text-gray-300 hover:tw-text-gray-400 hover:tw-border-gray-400" style="border-width:3px">
          <i class="fa fa-close fa-lg  tw-mb-0.5 tw-ml-0.5"></i>
        </div>
        <div class=" tw-h-8 tw-w-8 tw-rounded-full tw-border-3 tw-border-gray-300 tw-flex tw-items-center tw-justify-center  tw-mr-2 tw-text-gray-300 hover:tw-text-gray-400 hover:tw-border-gray-400" style="border-width:3px">
          <i class="fa fa-refresh fa-lg "></i>
        </div>
      </div>
      <div class=" tw-flex-grow tw-h-full tw-flex">
        <div class=" tw-h-8 tw-w-8 tw-rounded-full tw-border-3 tw-border-gray-300 tw-flex tw-items-center tw-justify-center tw-text-gray-300 hover:tw-text-gray-400 hover:tw-border-gray-400" style="border-width:3px">
          <i class="fa fa-question fa-lg "></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Blank',
  components: {
  },
  data(){
    return {

    }
  },
  created(){
  },
  mounted(){
  },
  watch:{
    '$route'(to , from) {
      this.$router.go(0)
      to;from;
    },
  },
  computed:{
    fullHeight(){
      return this.$store.state.fullHeight
    },
    fullWidth(){
      return this.$store.state.fullWidth
    },
    theme(){
      return this.$store.state.theme
    },
  },
  methods:{
  }
}
</script>

<style scoped>
.siyuan-heiti{
  font-family: "Noto Sans SC";
  font-weight: 400;
}

.glow-effect {
  box-shadow: 0 0 12px 0px rgba(70,134,250); /* outer cyan */
}
</style>