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
          {name:"名称1",role:"评论人1",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍1"},
          {name:"名称2",role:"评论人2",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍2"},
          {name:"名称3",role:"评论人3",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍3"},
          {name:"名称4",role:"评论人4",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍4"}
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
