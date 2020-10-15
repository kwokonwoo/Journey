<template>
    <div class="icons">
      <swiper>
        <swiper-slide v-for="(page, index) of pages" :key="index">
          <div
            class="icon"
            v-for="item of page"
            :key="item.id"
          >
              <div class="icon-img">
                <img class="icon-img-content" :src="item.imgUrl" />
              </div>
              <p class="icon-desc">{{item.desc}}</p>
          </div>
        </swiper-slide>
      </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        id: '0001',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/158387fe5376294f3776d01358d6b73b.png',
        desc: '景点门票'
      }, {
        id: '0002',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/69e8b07cb2d438c5530aebd4c8e3abd3.png',
        desc: '一日游'
      }, {
        id: '0003',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/bd121884123cceb4da978047423421ce.png',
        desc: '总统府'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
        desc: '牛首山'
      }, {
        id: '0005',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/158387fe5376294f3776d01358d6b73b.png',
        desc: '景点门啊啊啊啊啊啊啊啊啊'
      }, {
        id: '0006',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/c1/6f15f887179fa002.png',
        desc: '一日游'
      }, {
        id: '0007',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/c1/6f15f887179fa002.png',
        desc: '一日游'
      }, {
        id: '0008',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/f04285731d7121da1b9028e2bf431695.png',
        desc: '牛首山'
      }, {
        id: '0009',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/d706a4d71c57c53ee8863b75a7af30cf.png',
        desc: '牛首山'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    @import '~styles/mixins.styl'
    .icons >>> .swiper-container
      height: 0
      padding-bottom: 50%
    .icon
      position: relative
      overflow: hidden
      float: left
      width: 25%
      height: 0
      padding-bottom: 25%
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        .icon-img-content
          display: block
          margin: 0 auto
          height: 100%
      .icon-desc
        position: absolute
        left: 0
        right: 0
        bottom: 0
        height: .44rem
        line-height: .44rem
        text-align: center
        color: $darkTextColor
        ellipsis()
</style>
