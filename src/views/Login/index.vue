<template>
    <div id="map" class="map" :style="style">
    </div>
</template>
<script>
export default {
    data(){
        return{
            ratioHeigt:null,
            ratioWidth:null,
        }
    },
    computed:{
        style(){
            return {
              width:`${1/this.ratioWidth*100}%`,
              height:`${1/this.ratioHeigt*100}%`,
              transform: "scale("+ this.ratioWidth + ',' + this.ratioHeigt + ") ",
              transformOrigin: "left top ",
            }
        }
    },
    created(){
      window.addEventListener('resize',this.getHeight)
      this.getHeight()
    },
    methods:{
      getHeight(){
        this.ratioWidth = 1920/window.innerWidth
        this.ratioHeigt=1080/window.innerHeight
      },
    }
}
</script>
<style lang="scss">
    
</style>