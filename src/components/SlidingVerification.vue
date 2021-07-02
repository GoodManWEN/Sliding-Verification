<template>
  <div class="tw-h-88 tw-w-88 tw-bg-gray-50 tw-rounded-md tw-p-4">
    <div class=" tw-text-gray-400 tw-text-sm  tw-select-none">安全验证</div>
    <div class=" tw-text-gray-900 siyuan-heiti tw-text-xl tw-mt-1  tw-select-none">拖动下方滑块完成拼图</div>
    <div ref="image" class=" tw-mt-2 tw-select-none tw-overflow-hidden tw-bg-gray-400" style="height:168px">
      <div ref="floatbox" class="tw-w-12 tw-h-12 tw-relative ctn-drop-shadow" style="left:0px;top:-48px">
        <div class="tw-w-12 tw-h-12 cp-cp1">
          <div class="tw-w-full tw-h-full glow-inside cp-cp1 tw-relative" style="z-index:1" ></div>
          <div class="tw-relative" style="height:168px;width:320px;top:-148px">
            <img class="tw-object-cover tw-rounded-sm tw-w-full tw-h-full"  src="https://helpx.adobe.com/content/dam/help/en/photoshop/using/convert-color-image-black-white/jcr_content/main-pars/before_and_after/image-before/Landscape-Color.jpg">
          </div>
        </div>
      </div>
      <div ref="pit" class="cp-cp1 tw-relative tw-bg-gray-200" style="z-index:1;top:168px;left:0px;width:50px;height:50px;">
        <div class="tw-w-12 tw-h-12" style="background-color:rgba(80,80,80,.1);top:1px;left:1px;z-index:200"></div>
        <!-- 这里不知道怎么回事显示不正常 -->
        <div class="tw-w-12 tw-h-12 cp-cp1 tw-relative pit-inside" style="z-index:1;top:1px;left:1px">
          <div class="tw-relative" style="height:168px;width:320px;top:0px">
            <img class="tw-object-cover tw-rounded-sm tw-w-full tw-h-full"  src="https://helpx.adobe.com/content/dam/help/en/photoshop/using/convert-color-image-black-white/jcr_content/main-pars/before_and_after/image-before/Landscape-Color.jpg">
          </div>
        </div>
      </div>
      <div class=" tw-relative" style="height:168px;width:320px;top:-96px">
        <img class="tw-object-cover tw-rounded-sm tw-w-full tw-h-full"  src="https://helpx.adobe.com/content/dam/help/en/photoshop/using/convert-color-image-black-white/jcr_content/main-pars/before_and_after/image-before/Landscape-Color.jpg">
      </div>
      <!-- 
        https://helpx.adobe.com/content/dam/help/en/photoshop/using/convert-color-image-black-white/jcr_content/main-pars/before_and_after/image-before/Landscape-Color.jpg
        https://img2.baidu.com/it/u=4064921610,597246006&fm=26&fmt=auto&gp=0.jpg
       -->
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
      image_height:168,
      image_width:320,
      box_height:48,
      box_width:48,
      image_height_abs:0,
      image_width_abs:0,
      image_height_fix:0,
      image_width_fix:0,
    }
  },
  created(){
  },
  mounted(){
    let random_height_range = this.image_height * 0.8 - this.box_height
    this.image_height_abs = Math.floor(random_height_range * Math.random() + this.image_height * 0.1) 
    let random_width_range = this.image_width * 0.4 - this.box_width
    this.image_width_abs = Math.floor(random_width_range * Math.random() + this.image_width * 0.55) 
    let image_height_display = this.image_height_abs - 48
    this.$refs.pit.style.top = image_height_display+'px'
    this.$refs.pit.style.left = this.image_width_abs+'px'
    this.$refs.pit_img.style.left = -this.image_width_abs+'px'
    console.log(this.image_height_abs,this.image_width_abs,image_height_display)
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

.glow-effect{
  box-shadow: 0 0 12px 0px rgba(70,134,250); 
}

.glow-inside{
  box-shadow: 0 0 12px 6px rgba(255,255,255,1) inset;
}

.pit-inside{
  box-shadow: 0 0 14px 3px rgba(0,0,0,1) inset;
}

.ctn-drop-shadow{
  filter: drop-shadow(0px 0px 5px rgba(40,40,40,1));
  z-index:2;
}

.cp-cp1{
  -webkit-clip-path: polygon(30% 0%, 70% 0%, 100% 30%, 100% 70%, 70% 100%, 30% 100%, 0% 70%, 0% 30%);
  clip-path: polygon(30% 0%, 70% 0%, 100% 30%, 100% 70%, 70% 100%, 30% 100%, 0% 70%, 0% 30%);
}

.cp-cp2{
  -webkit-clip-path: polygon(50% 0%, 100% 38%, 82% 100%, 18% 100%, 0% 38%);
  clip-path: polygon(50% 0%, 100% 38%, 82% 100%, 18% 100%, 0% 38%);
}

.cp-cp3{
  -webkit-clip-path: polygon(25% 0%, 100% 1%, 100% 100%, 25% 100%, 0% 50%);
  clip-path: polygon(25% 0%, 100% 1%, 100% 100%, 25% 100%, 0% 50%);
}

.cp-cp4{
  -webkit-clip-path: polygon(0% 0%, 75% 0%, 100% 50%, 75% 100%, 0% 100%);
  clip-path: polygon(0% 0%, 75% 0%, 100% 50%, 75% 100%, 0% 100%);
}

.cp-cp5{
  -webkit-clip-path: polygon(100% 0%, 75% 50%, 100% 100%, 25% 100%, 0% 50%, 25% 0%);
  clip-path: polygon(100% 0%, 75% 50%, 100% 100%, 25% 100%, 0% 50%, 25% 0%);
}

.cp-cp6{
  -webkit-clip-path: polygon(75% 0%, 100% 50%, 75% 100%, 0% 100%, 25% 50%, 0% 0%);
  clip-path: polygon(75% 0%, 100% 50%, 75% 100%, 0% 100%, 25% 50%, 0% 0%);
}
</style>