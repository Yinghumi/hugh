<template>
  <div>
    <i-grid i-class="no-border">
    <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>
 </i-grid>
 <i-panel :title="title_name">
    <view style="padding: 15px;">
      <i-card v-for="item in top" :key="item" i-class="spilt" :extra="item.name" :thumb="item.image">
         <view slot="content">{{item.remark}}</view>
         <view slot="footer">{{item.role}}</view>
      </i-card>
    </view>
 </i-panel>
  </div>
</template>

<script>
export default {
  data () {
      return {
        title_name:"热门",
        grids:[
          {title:"音乐",image:"/static/images/1.png"},
          {title:"电视",image:"/static/images/2.png"},
          {title:"电影",image:"/static/images/3.png"},
          {title:"话剧",image:"/static/images/4.png"},
        ],
        top:[
             {"name":"《辛亥革命》","role":"回复：","image":"http://5b0988e595225.cdn.sohucs.com/images/20180126/db1e97ebec88481384e7c87457481e46.jpeg","remark":"革命战争片是真的催泪啊，此生不悔入华夏，来生还愿种花家"},
             {"name":"《你好，之华》","role":"回复：","image":"http://wx4.sinaimg.cn/wap720/41de2dbdly1fx5j47s0ncj21be0qo7c5.jpg","remark":"胡先生在里面是一个反派角色，但是演技超棒。"},
             {"name":"《南方车站的聚会》","role":"回复：","image":"http://wx2.sinaimg.cn/large/006MYXpkgy1g9g158yilsj30u00gv7wh.jpg","remark":"我胡的一重大突破！一场罪与罚的角逐，但是最后还是有人性的光辉 。"},
             {"name":"《攀登者》","role":"回复：","image":"http://n.sinaimg.cn/sinacn20191122ac/733/w469h264/20191122/004f-iittafq8672618.jpg","remark":"戏里戏外都为登山者们感到骄傲。"}
             ],
             
      indicatorDots: true,
      autoplay: true,
      interval: 5000,
      duration: 1000,
    }
  },


  methods: {
    goType (type) {
      console.log(type)
      let url = '../list/main?type=' + type.title
      mpvue.navigateTo({url})
    }
  },

    
  created () {
  }
}
</script>

<style scoped>
div >>> .no-border{
  border-width: 0pt;
}
div >>> .split{
  border-bottom:10pt;
}
</style>
