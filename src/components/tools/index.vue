<template>
  <div class="orderbook-tools">
    <div class="orderbook-tools-item">
      <button class="selected">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          fill="none"
          class="css-8qwo6f"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M10.003 9.342H22v1.2H10.003v-1.2zm0 2.455H22v1.202H10.003v-1.202zM22 14.253H10.003v1.201H22v-1.2z"
            fill="#8A8A8A"
          ></path>
          <path
            d="M5.668 7.299l1.733 3.11 1.487-2.302h13.108v-1.2H8.235l-.758 1.172L5.762 5 3.326 8.644H2v1.2h1.967L5.668 7.3z"
            fill="#F84960"
          ></path>
          <path
            d="M7.402 14.391l-1.732 3.11-1.702-2.545H2v1.2h1.326L5.763 19.8l1.715-3.079.758 1.173h13.76v-1.201H8.89l-1.487-2.302z"
            fill="#2EBD85"
          ></path>
        </svg>
      </button>
      <button>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          fill="none"
          class="css-8qwo6f"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M22 7H2v1.2h20V7zm0 2.427H10.003v1.2H22v-1.2zm-11.997 2.454H22v1.2H10.003v-1.2zM22 14.336H10.003v1.2H22v-1.2z"
            fill="#8A8A8A"
          ></path>
          <path
            d="M7.402 14.474L5.67 17.582l-1.702-2.544H2v1.2h1.326l2.436 3.642 1.715-3.078.758 1.173h13.76v-1.2H8.889l-1.487-2.301z"
            fill="#2EBD85"
          ></path>
        </svg>
      </button>
      <button>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          fill="none"
          class="css-8qwo6f"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M22 9.337H10.003v1.2H22v-1.2zm0 2.452H10.003v1.2H22v-1.2zm-11.997 2.453H22v1.2H10.003v-1.2zM22 16.681H2v1.199h20v-1.2z"
            fill="#8A8A8A"
          ></path>
          <path
            d="M5.668 7.296l1.733 3.106 1.487-2.299h13.108v-1.2H8.235l-.758 1.172L5.761 5 3.326 8.639H2v1.2h1.967l1.701-2.543z"
            fill="#F84960"
          ></path>
        </svg>
      </button>
    </div>
    <div class="orderbook-tools-item">
      <orderbook-dropdown />
    </div>
  </div>
</template>

<style lang="scss">
.orderbook-tools {
  display: flex;
  justify-content: space-between;
  align-items: center;
  .orderbook-tools-item {
    margin-top: 15px;
    button {
      background-color: transparent;
      width: 30px;
      border: none;
      outline: none;
      padding: 0 3px;
      border-radius: 0.2rem;
      transition: 0.2s;
      margin-right: 5px;
      cursor: pointer;
      &.selected {
        background-color: rgba($color: rgb(209, 209, 209), $alpha: 0.2);
      }
    }
  }
}
</style>

<script>
import orderbookDropdown from './dropdown'
export default {
  components: { orderbookDropdown },
}
</script>
