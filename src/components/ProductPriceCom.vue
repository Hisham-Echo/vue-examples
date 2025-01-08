<template>
  <div class="com">
    <div class="product">
      <h3>title</h3>
      <p>description</p>
      <span class="price">price: ${{ price }}</span>
      <span class="amount-title">amount:</span>
      <input type="number" min="1" max="20" step="1" v-model="amount" />
      <div class="total-price">
        <div class="amount">Amount:</div>
        <div class="total">Total: ${{ totalPrice }}</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.com {
  text-align: center;
  padding: 20px;
}
.product {
  width: 300;
  background-color: #eee;
  padding: 20px;
  margin: 20px;
  h3 {
    margin: 0 0 10px;
    color: #777;
  }
  .price {
    display: block;
    font-size: 14px;
    margin: 0 0 20px;
  }
  .amount-title {
    font-size: 14px;
    text-align: center;
    display: block;
    margin-bottom: 20px;
  }
  input[type="range"] {
    width: 100%;
    padding: 5px;
  }
  .total-price {
    overflow: hidden;
    padding-top: 20px;
    .amount,
    .total {
      background-color: #fff;
      padding: 2px 10px;
      border-radius: 4px;
    }
    .amount {
      float: left;
    }
    .total {
      float: right;
    }
  }
}
</style>

<script>
export default {
  name: "ProductPriceCom",
  data() {
    return {
      amount: 1,
      price: 50,
    };
  },
  computed: {
    totalPrice: function () {
      return this.amount * this.price;
    },
  },
};
</script>
