<template>
  <div>
    <p style="color: cornflowerblue">带刮卡的刮刮卡</p>
    <p>
      <a style="text-align: center;margin-right: 20px;font-size: 16px" @click="changeTouch">可以刮动</a>
      <a style="font-size: 16px;text-align: center" @click="changeTouch1">不可以刮动</a>
    </p>
    <p>
      <a style="text-align: center;margin-right: 20px;font-size: 16px" @click="changeTouchSpotImg">更换刮片</a>
      <a style="font-size: 16px;text-align: center" @click="changeImg">更换图片</a>
    </p>
    <guaguaka-ui ref="guaguaka" :guaguakaConfig="guaguakaConfig" id="guaguakaDiv" @success="guaguakaSuccess"></guaguaka-ui>
    <p style="color: cornflowerblue">没刮卡的刮刮卡</p>
    <p><a style="font-size: 16px;text-align: center" @click="changeImg1">更换图片</a></p>
    <guaguaka-ui ref="guaguaka1" :guaguakaConfig="guaguakaConfig1" id="guaguakaDiv1" @success="guaguakaSuccess"></guaguaka-ui>
    <!--<guaguaka ref="guaguaka1" id="guaguakaDiv1"></guaguaka>-->
  </div>
</template>

<script>
import guaguakaUi from 'guaguaka-ui'
export default {
  components: {
    guaguakaUi
  },
  data () {
    return {
      guaguakaConfig: {
        id: 'guaguakaDiv',
        width: '307.5px',
        height: '165px',
        isTouch: true,
        visibleArea: 30,
        touchSpotShow: true,
        touchSpotImg: 'https://i.loli.net/2019/01/17/5c3ffe3dbafa3.png',
        touchSpotSize: '10px',
        touchSpotImgWidth: '30px',
        touchSpotImgHeight: '50px',
        touchSpotPosition: '0.2 0.1',
        prizeImg: 'http://t2.hddhhn.com/uploads/tu/201610/198/scx30045vxd.jpg'
      },
      guaguakaConfig1: {
        id: 'guaguakaDiv1',
        width: '307.5px',
        height: '165px',
        isTouch: true,
        touchSpotShow: false,
        visibleArea: 30
      }
    }
  },
  computed: {},
  mounted () {
  },
  methods: {
    changeTouch () {
      this.$refs.guaguaka.setInfo({
        isTouch: true
      })
    },
    changeTouchSpotImg () {
      this.$refs.guaguaka.setInfo({
        touchSpotImg: 'https://i.loli.net/2019/01/17/5c3fef16bbd5a.png',
        touchSpotImgWidth: '20px',
        touchSpotImgHeight: '20px',
        touchSpotPosition: '0.5 0.5',
        touchSpotSize: '20px',
        isTouch: true
      })
    },
    changeTouch1 () {
      this.$refs.guaguaka.setInfo({
        isTouch: false
      })
    },
    changeImg () {
      this.$refs.guaguaka.setInfo({
        prizeImg: 'http://img.zcool.cn/community/01e3eb59a45598a801211d25be7207.jpg@2o.jpg',
        isTouch: true
      })
    },
    changeImg1 () {
      this.$refs.guaguaka1.setInfo({
        prizeImg: 'http://img.zcool.cn/community/01e3eb59a45598a801211d25be7207.jpg@2o.jpg',
        isTouch: true
      })
    },
    guaguakaSuccess (data) {
      alert(data + '刮卡成功')
    }
  }
}
</script>

<style scoped lang="scss">
  #guaguakaDiv{
    width: 307.5px;
    margin: auto;
  }
  #guaguakaDiv1{
    width: 307.5px;
    margin: auto;
  }
</style>
