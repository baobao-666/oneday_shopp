<template>
  <div class="Clearing_wrap">
    <h2>结算页</h2>
    <div class="Clearing_ul">
      <li
        class="li"
        @click="change(index)"
        :class="{active:curIndex===index}"
        v-for="(item,index) in list"
        :key="index"
      >
        <img :src="item.img" alt />
        <span>{{item.title}}</span>
      </li>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: [
        {
          title: "支付宝",
          img: require("../../images/支付宝认证.png")
        },
        {
          title: "微信",
          img: require("../../images/微信.png")
        },
        {
          title: "银联",
          img: require("../../images/支付平台-银联.png")
        }
      ],
      curIndex: 0
    };
  },
  methods: {
    change(index) {
      this.curIndex = index;
    }
  }
};
</script>

<style lang="scss" scoped>
.Clearing_wrap {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}
h2{
  width: 100%;
 line-height: 60px;
 text-align: center;
 border-bottom: 2px solid ;
}
.Clearing_ul {
  width: 100%;
  .li {
    width: 100%;
    line-height: 50px;
    display: flex;
    align-items: center;
    border-bottom: 1px solid #ccc;
    &.active {
      background-image: url("../../images/check.png");
      background-repeat: no-repeat; 
      background-position-y: center;
      background-position-x: right;
    }
    img {
      width: 40px;
      height: 40px;
      margin: 30px;
    }
  }
}
</style>