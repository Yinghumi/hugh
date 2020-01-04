<template>
  <div>
      <i-card v-for="item in list" :key="item" i-class="spilt" :extra="item.name" :thumb="item.image">
         <view slot="content">{{item.remark}}</view>
         <view slot="footer">{{item.role}}</view>
      </i-card>
  </div>
</template>

<script>
export default {
  data () {
      return {
        list:[]
    }
  },
  onLoad (option){
    //console.log(option.type)
     this.list = require('@/data/' + option.type + '.json')
     console.log(this.list)
  },
  methods: {
    },
    
  created () {
  }
}
</script>

<style scoped>
div >>> .split{
  border-bottom:10pt;
}
</style>
