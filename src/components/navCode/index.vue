<template>
   <div class="home_nav">
      <span
        :class="{active:curIndexs===index}"
        @click="change(index)"
        v-for="(item,index) in navList"
        :key="index"
      >{{item}}</span>
    </div>
</template>

<script>
export default {
props:['navList','curIndexs'],
methods: {
  change(index){
     this.$emit('change',index)
  }
}
}
</script>

<style lang="scss" scoped>
.home_nav {
  width: 90%;
  height: 60px;
  display: flex;
  margin-left: 5%;
  border-bottom: 1px solid #ccc;
  span {
    flex: 1;
    text-align: center;
    line-height: 60px;
    &.active {
      color: skyblue;
    }
  }
}
</style>