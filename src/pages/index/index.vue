<template>
  <div>
     <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
      style="height:200px"
    >
    <block v-for="item in imgUrls" :key="item">
      <swiper-item>
        <image :src="item" style="width:100%;"/>
      </swiper-item>
    </block>
  </swiper>
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
             {"name":"《辛亥革命》","role":"窈窕弦歌","image":"http://5b0988e595225.cdn.sohucs.com/images/20180126/db1e97ebec88481384e7c87457481e46.jpeg","remark":"《辛亥革命》是由张黎和成龙执导，赵文瑄、李冰冰、陈冲、孙淳、房祖名、胡歌、余少群、杜宇航等主演的革命战争片。该片讲述了晚清末年，内忧外患，中华民族到了危亡之际。改良派维新变法运动的失败，孙中山为首的革命派，决心以革命推翻清政府，建立共和体制的故事。"},
             {"name":"《你好，之华》","role":"浮华","image":"http://wx4.sinaimg.cn/wap720/41de2dbdly1fx5j47s0ncj21be0qo7c5.jpg","remark":"该片讲述了人生的“一期一会”，袁之华代替姐姐参加同学会并偶遇年少时仰慕的男生尹川，二人信件往来间以各自视角引出三代人的故事纠葛。"},
             {"name":"《南方车站的聚会》","role":"humi","image":"http://wx2.sinaimg.cn/large/006MYXpkgy1g9g158yilsj30u00gv7wh.jpg","remark":"影片故事灵感来源于真实新闻事件，讲述了偷车团伙头目周泽农，在重金悬赏下走上逃亡之路，艰难寻求自我救赎的故事 。"},
             {"name":"《攀登者》","role":"歌以咏志","image":"http://n.sinaimg.cn/sinacn20191122ac/733/w469h264/20191122/004f-iittafq8672618.jpg","remark":"影片以1960年与1975年中国登山队两次登顶珠峰的事迹为背景，讲述方五洲、曲松林等中国攀登者怀揣着最纯粹的梦想集结于珠峰，肩负时代使命于世界之巅的故事。"}
             ],
           imgUrls: [
    'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1578137639960&di=1c0c229986364b80ebbbcdba665db048&imgtype=0&src=http%3A%2F%2Fhbimg.b0.upaiyun.com%2F933b3ee259a9196b6b796d9ee9c88a177c06614c3bd35-xkZ0vw_fw658',
    'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=2138540041,3871512787&fm=26&gp=0.jpg',
    'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1578137748150&di=fe6787124f511c662c04dfe005f8b03f&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201603%2F17%2F20160317164103_FEySx.jpeg'
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
