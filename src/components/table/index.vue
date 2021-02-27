<template>
  <div class="table">
    <div class="table-header row">
      <div class="table-header-item row-item flex-start">Price(USDT)</div>
      <div class="table-header-item row-item flex-end">Amount(BTC)</div>
      <div class="table-header-item row-item flex-end">Total</div>
    </div>
    <ask-orders :orders="data.asks" />
    <div class="live-details">
      <div :class="['current-price', currentPriceStatus]">
        ${{ +data.bids[0][0] }}
        <font-awesome-icon
          :icon="currentPriceStatus == 'green' ? 'arrow-up' : 'arrow-down'"
        />
      </div>
      <div class="market-price">${{ +data.bids[0][0] }}</div>
      <div class="more-details">
        More
        <font-awesome-icon icon="signal" class="more-icon" />
      </div>
    </div>
    <bid-orders :orders="data.bids" />
  </div>
</template>

<style lang="scss">
.table {
  font-size: 0.93rem;
  .row {
    font-size: 0.8rem;
    display: flex;
    .row-item {
      display: flex;
      flex: 1 1 0%;
      z-index: 1;
    }
    cursor: pointer;
    .order-amount,
    .order-total {
      color: white;
      opacity: 0.7;
    }
  }
  .table-header {
    color: rgba($color: #fff, $alpha: 0.5);
    margin-top: 10px;
  }
  .live-details {
    margin: 15px 0 7px 0;
    display: flex;
    justify-content: space-between;
    color: white;
    align-items: center;
    .current-price {
      &.red {
        color: #f6465d;
      }
      &.green {
        color: #00c582;
      }
    }
    .more-details {
      font-size: 0.8rem;
      .more-icon {
        color: #00c582;
        margin-left: 3px;
      }
    }
  }
}
</style>

<script>
import askOrders from './ask'
import bidOrders from './bid'
export default {
  props: ['data'],
  data() {
    return {
      currentPriceStatus: 'green',
    }
  },
  components: {
    askOrders,
    bidOrders,
  },
  watch: {
    data: function(val, lastVal) {
      this.currentPriceStatus =
        val.asks[0][0] > lastVal.asks[0][0] ? 'green' : 'red'
    },
  },
}
</script>
