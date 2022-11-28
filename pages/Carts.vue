<template>
  <div>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.1.2/dist/tailwind.min.css" rel="stylesheet">
    <Navbar />
    <div class="relative flex items-top justify-center min-h-screen bg-gray-100 sm:items-center sm:pt-0">
      <!-- <div class="cart" v-for="item in items"> -->
        <!-- <div v-if="$auth.loggedIn"></div> -->
        <div v-for="item in cards" :key="item.id">
          <h4>項目</h4>
          <h2>購物車</h2>
          <div class="flex">
            <div>{{ item.id }}</div>
            <div>{{ item.name }}</div>
            <div>{{ item.courses.price }}</div>
            <h4>售價</h4>
            <h4>結帳金額</h4>
          </div>
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
</template>

<script>
import Navbar from '../components/Navbar.vue'
export default {
  components: { Navbar },
  data() {
    return {
      itemInCart: {
        "items": [
          {
            "id": "",
            "coupon": ""
          }
        ],
      },
      hiskio_token:'',
      cards: [],
    }
  },
  mounted() {
    this.hiskio_token = document.cookie.split('=')[1];
    fetch('https://api.hiskio.com/v2/carts', {
      method: 'POST',
      headers: {
        'accept': 'application/json',
        'Content-Type': 'application/json',
        'Authorization': `Bearer ${this.hiskio_token}`,
        body:'',
      },
    })
      .then(response => response.json())
      .then(arr => this.cards = arr.data)
  }

}
</script>

<style>

</style>