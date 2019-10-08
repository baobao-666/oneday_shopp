<template>
  <div class="cart_wrap">
    <main>
      <CartCode></CartCode>
    </main>
    <footer>
      <div class="allPrice">
        总价:
        <span>{{total}}</span>
      </div>
      <div class="jump">
        <router-link to="/Clearing">跳转</router-link>
      </div>
    </footer>
  </div>
</template>

<script>
import CartCode from "../../components/cartListCode/";
import { mapState } from "vuex";
export default {
  components: {
    CartCode
  },
  computed: {
    ...mapState(["curList"]),
    total() {
      return this.curList.reduce((a, b) => {
        return a + b.count * b.price;
      }, 0);
    }
  }
};
</script>

<style lang="scss" scoped>
.cart_wrap {
  width: 100%;
  height: 100%;
  background: #f0f0ff;
  display: flex;
  flex-direction: column;
}
main {
  flex: 1;
}
footer {
  width: 100%;
  line-height: 60px;
  border-top: 1px solid #666;
  display: flex;
  .allPrice {
    flex: 4;
    padding-left: 30px;
    border-right: 1px solid #f4f4ff;
  }
  .jump {
    flex: 1;
    text-align: center;
    a {
    text-decoration: none;
    color: #000;
}
  }
}
</style>