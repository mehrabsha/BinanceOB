<template>
  <div class="orderbook-dropdown-btn" @click="show = !show">
    0.01
    <font-awesome-icon icon="sort-down" class="orderbook-dropdown-icon" />
    <div class="orderbook-dropdown-items" v-show="show">
      <div class="orderbook-dropdown-item">0.01</div>
      <div class="orderbook-dropdown-item">0.1</div>
      <div class="orderbook-dropdown-item">1</div>
      <div class="orderbook-dropdown-item">10</div>
      <div class="orderbook-dropdown-item">50</div>
      <div class="orderbook-dropdown-item">100</div>
    </div>
  </div>
</template>

<style lang="scss">
.orderbook-dropdown-btn {
  border-radius: 0.2rem;
  padding: 2px 5px;
  color: white;
  z-index: 999;
  font-size: 0.8rem;
  position: relative;
  background-color: rgba($color: #fff, $alpha: 0.1);
  cursor: pointer;
  .orderbook-dropdown-icon {
    opacity: 0.5;
    margin: 0 3px;
    padding-bottom: 2px;
  }
  .orderbook-dropdown-items {
    position: absolute;
    border-radius: 0.2rem;
    width: 100%;
    left: 0;
    margin-top: 5px;
    background-color: #323439;
    text-align: center;
    .orderbook-dropdown-item {
      opacity: 0.5;
      transition: 0.2s;
      padding: 3px 0;
      &:hover {
        opacity: 1;
        background-color: rgba($color: #fff, $alpha: 0.2);
      }
    }
  }
}
</style>

<script>
export default {
  data() {
    return {
      show: false,
    }
  },
}
</script>
