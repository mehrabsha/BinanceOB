<template>
  <div class="orderbook">
    <div class="orderbook-header">
      <div class="orderbook-title">Order Book</div>
      <font-awesome-icon icon="times" class="orderbook-close" />
    </div>
    <orderbook-tools />
    <orderbook-table :data="data" />
  </div>
</template>

<style lang="scss">
@font-face {
  font-family: 'IBM Plex Sans';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: url(~@/assets/fonts/IBMPlexSans-Medium.ttf);
}
html {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  font-size: 16px;
  background-color: #2b3139;
}
.orderbook {
  background-color: #1b1d23;
  width: 300px;
  font-family: 'IBM Plex Sans';
  padding: 15px;
  border-radius: 0.5rem;
  .orderbook-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    .orderbook-close {
      color: white;
      opacity: 0.7;
      transition: 0.2s;
      cursor: pointer;
      &:hover {
        opacity: 1;
      }
    }
    .orderbook-title {
      color: white;
      font-size: 0.9rem;
      font-weight: bold;
    }
  }
  .flex-end {
    justify-content: flex-end;
  }
  .flex-start {
    justify-content: flex-start;
  }
}
</style>
<script>
import orderbookTools from '@/components/tools'
import orderbookTable from '@/components/table'
export default {
  data() {
    return {
      data: { asks: [[0, 0]], bids: [[0, 0]] },
    }
  },
  components: {
    orderbookTools,
    orderbookTable,
  },
  mounted() {
    let vm = this
    var connection = new WebSocket(
      'wss://stream.binance.com:9443/ws/btcusdt@depth10@1000ms'
    )
    connection.onmessage = function(event) {
      vm.data = JSON.parse(event.data)
    }
  },
}
</script>
