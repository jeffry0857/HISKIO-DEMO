<template>
  <div class="relative flex items-top justify-center min-h-screen bg-gray-100 sm:items-center sm:pt-0">
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.1.2/dist/tailwind.min.css" rel="stylesheet">
      <div class="wrapper flex">
        <div class="cart">
          <h2>購物車</h2>
          <div class="flex">
            <h4>項目</h4>
            <h4>售價</h4>
            <h4>結帳金額</h4>
          </div>
        </div>
        <div class="sub-total">
          <h2>小計</h2>
            <span>輸入折扣代碼</span>
            <input type="text">
            <button>確定</button>
            <a href="#">選擇抵用券</a>
            <hr>
            <div class="amount-container flex">
              <span>金額</span>
              <div class="amount">NT${{  }}</div>
            </div>
            <h3>NT${{  }}</h3>
            <button class="bg-red-500">前往結帳</button>
          </div>
        </div>
  </div>
</template>

<script>
export default {

  data() {
    return {
      course: {
        items: [
          {
            "id": "",
            "coupon": ""
          }
        ],
        coupons: []
      },
      hiskio_token:'',
    }
  },
  // mounted() {
  //   console.log(`Token : ${document.cookie}`);
  //   fetch('https://api.hiskio.com/v2/carts', {
  //     method: 'POST',
  //     headers: {
  //       'accept': 'application/json',
  //       'Content-Type': 'application/json',
  //       'Authorization': `Bearer ${hiskio_token}`
  //     },
  //     body: JSON.stringify(this.course),
  //   })
  // }

}
</script>

<style>

</style>