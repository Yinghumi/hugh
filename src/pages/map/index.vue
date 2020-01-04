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
        title_name:"热贴",
        grids:[
          {title:"音乐",image:"/static/images/1.png"},
          {title:"电视",image:"/static/images/2.png"},
          {title:"电影",image:"/static/images/3.png"},
          {title:"话剧",image:"/static/images/4.png"},
        ],
        top:[
          {name:"名称1",role:"回复1",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"评论1"},
          {name:"名称2",role:"回复2",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"评论2"},
          {name:"名称3",role:"回复3",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"评论3"},
          {name:"名称4",role:"回复4",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"评论4"}
        ],
          
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

/*<style scoped>
div >>> .no-border{
  border-width: 0pt;
}
div >>> .split{
  border-bottom:10pt;
}
</style>
