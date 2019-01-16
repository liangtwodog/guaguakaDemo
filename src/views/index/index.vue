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
    <guaguaka-ui ref="guaguaka" :guaguakaInfo="guaguakaInfo" id="guaguakaDiv" @success="guaguakaSuccess"></guaguaka-ui>
    <p style="color: cornflowerblue">没刮卡的刮刮卡</p>
    <p><a style="font-size: 16px;text-align: center" @click="changeImg1">更换图片</a></p>
    <guaguaka-ui ref="guaguaka1" :guaguakaInfo="guaguakaInfo1" id="guaguakaDiv1" @success="guaguakaSuccess"></guaguaka-ui>
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
      guaguakaInfo: {
        id: 'guaguakaDiv',
        width: 307.5,
        height: 165,
        isTouch: true,
        touchSpotSize: 20,
        visibleArea: 30,
        touchSpotShow: true,
        prizeImg: 'http://t2.hddhhn.com/uploads/tu/201610/198/scx30045vxd.jpg'
      },
      guaguakaInfo1: {
        id: 'guaguakaDiv1',
        width: 307.5,
        height: 165,
        isTouch: true,
        touchSpotSize: 20,
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
        touchSpotImg: 'https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1547195400&di=05806093ea518381728dd6506565ce8b&src=http://img4q.duitang.com/uploads/item/201109/02/20110902193607_CPrxv.thumb.700_0.jpg',
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

<style scoped>
  #guaguakaDiv{
    width: 307.5px;
    margin: auto;
    border-radius: 20px;
    overflow: hidden;
  }
  #guaguakaDiv1{
    width: 307.5px;
    margin: auto;
  }
</style>
