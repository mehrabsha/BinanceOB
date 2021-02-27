<template>
  <div class="table-bid-orders">
    <div class="bid-order row" v-for="(order, index) in orders" :key="index">
      <div class="order-price row-item flex-start">{{ +order[0] }}</div>
      <div class="order-amount row-item flex-end">{{ order[1] }}</div>
      <div class="order-total row-item flex-end">
        {{ (order[0] * order[1]).toFixed(2) }}
      </div>
      <div
        class="bg"
        :style="'transform : translateX(' + Math.random() * 100 + '%)'"
      ></div>
    </div>
  </div>
</template>

<style lang="scss">
.bid-order {
  overflow: hidden;
  position: relative;
  padding: 2px 0;
  .order-price {
    color: #00c582;
  }
  .bg {
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: #183630;
    z-index: 0;
  }
}
</style>

<script>
export default {
  props: {
    orders: {
      type: Array,
      // Object or array defaults must be returned from
      // a factory function
      default: function() {
        return [[0, 0]]
      },
    },
  },
}
</script>
