<template>
  <div>
    <div class="wrapper" id="haha" ref="haha">

    </div>
    <div class="btn">
      <text @click="changeColor">改变颜色</text>
      <text @click="reset">重置</text>
      <text @click="changeWidth">改变长度</text>
    </div>
  </div>


</template>

<script>
const animation = weex.requireModule('animation')
export default {
  
  data () {
    return {
    }
  },
  methods: {
    changeColor() {
      document.getElementById('haha').style.backgroundColor = 'blue'
    },
    reset() {
      document.getElementById('haha').style.backgroundColor = 'red'
      document.getElementById('haha').style = {
        backgroundColor : 'red',
        width : '200px,',
        height : '200px'
      }
    },
    changeWidth() {
      animation.transition(this.$refs.haha,{
        styles:{
          width: '400px'
        },
        duration: 0,
        timingFunction: 'ease',
        delay: 0
      }, function(){

      })
    }
  
  }

}
</script>

<style scoped>
  .wrapper{
    width: 200px;
    height: 200px;
    background-color: red;
  }
  .btn{
    justify-content: space-between;
    align-items: center;
    flex-direction: row;
    padding: 40px;
  }

</style>
