<template>
  <div class="modal-overlay" @click="$emit('close-modal')">
    <div class="modal" @click.stop>
      <div class="bg-gray-100 flex rounded-2xl shadow-lg max-w-3xl p-5 items-center">
        <!-- form -->
        <div class="md:w-1/2 px-8 md:px-16">
          <h2 class="font-bold text-2xl text-[#002D74]">Login</h2>
          <button class="bg-white border py-2 w-full rounded-xl mt-5 flex justify-center items-center text-sm hover:scale-105 duration-300 text-[#002D74]">
            <svg width="28" height="28" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M28 26.25C27.9997 26.714 27.8153 27.159 27.4871 27.4871C27.159 27.8153 26.714 27.9997 26.25 28H1.75C1.28595 27.9997 0.840987 27.8153 0.512856 27.4871C0.184725 27.159 0.000264943 26.714 0 26.25L0 1.75C0.000264943 1.28595 0.184725 0.840987 0.512856 0.512856C0.840987 0.184725 1.28595 0.000264943 1.75 0L26.25 0C26.714 0.000264943 27.159 0.184725 27.4871 0.512856C27.8153 0.840987 27.9997 1.28595 28 1.75V26.25Z" fill="#3B5998"/>
            <path d="M19.249 28V17.5H22.749L23.624 13.123H19.249V11.365C19.1989 11.0089 19.2322 10.6461 19.3462 10.3051C19.4602 9.96405 19.6519 9.65418 19.9061 9.39988C20.1603 9.14557 20.4701 8.95377 20.8111 8.83961C21.1521 8.72544 21.5149 8.69203 21.871 8.74199H23.622V4.36499H20.122C16.908 4.36499 14.871 6.88699 14.871 10.493V13.119H11.371V17.496H14.871V27.996L19.249 28Z" fill="white"/>
            </svg>
            使用Facebook登入
          </button>
          <button class="bg-white border py-2 w-full rounded-xl mt-5 flex justify-center items-center text-sm hover:scale-105 duration-300 text-[#002D74]">
            <svg class="mr-3" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 48" width="25px">
              <path fill="#FFC107" d="M43.611,20.083H42V20H24v8h11.303c-1.649,4.657-6.08,8-11.303,8c-6.627,0-12-5.373-12-12c0-6.627,5.373-12,12-12c3.059,0,5.842,1.154,7.961,3.039l5.657-5.657C34.046,6.053,29.268,4,24,4C12.955,4,4,12.955,4,24c0,11.045,8.955,20,20,20c11.045,0,20-8.955,20-20C44,22.659,43.862,21.35,43.611,20.083z" />
              <path fill="#FF3D00" d="M6.306,14.691l6.571,4.819C14.655,15.108,18.961,12,24,12c3.059,0,5.842,1.154,7.961,3.039l5.657-5.657C34.046,6.053,29.268,4,24,4C16.318,4,9.656,8.337,6.306,14.691z" />
              <path fill="#4CAF50" d="M24,44c5.166,0,9.86-1.977,13.409-5.192l-6.19-5.238C29.211,35.091,26.715,36,24,36c-5.202,0-9.619-3.317-11.283-7.946l-6.522,5.025C9.505,39.556,16.227,44,24,44z" />
              <path fill="#1976D2" d="M43.611,20.083H42V20H24v8h11.303c-0.792,2.237-2.231,4.166-4.087,5.571c0.001-0.001,0.002-0.001,0.003-0.002l6.19,5.238C36.971,39.205,44,34,44,24C44,22.659,43.862,21.35,43.611,20.083z" />
            </svg>
            使用Google登入
          </button>
          <form class="flex flex-col gap-4">
            <input v-model="user.account" class="p-2 mt-8 rounded-xl border" type="text" name="account" placeholder="請輸入HiSKIO ID">
            <div class="relative">
              <input v-model="user.password" class="p-2 rounded-xl border w-full" type="password" name="password" placeholder="請輸入登入密碼">
            </div>
          </form>
          <button @click="submitForm" class="bg-[#002D74] rounded-xl py-2 hover:scale-105 duration-300">登入</button>
          <div class="mt-5 text-xs border-b border-[#002D74] py-4 text-[#002D74]">
            <a href="#">Forgot your password?</a>
          </div>
        
          <div class="mt-3 text-xs flex justify-between items-center text-[#002D74]">
            <p>Don't have an account?</p>
            <button class="py-2 px-5 bg-white border rounded-xl hover:scale-110 duration-300">Register</button>
          </div>
        </div>
      </div>
    </div>
    <div class="close" @click="$emit('close-modal')">
      <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M8.51339 6.99915L13.0835 2.42733C13.2845 2.22666 13.3974 1.95443 13.3975 1.67054C13.3976 1.38664 13.2848 1.11433 13.0841 0.913519C12.8833 0.712704 12.6109 0.599831 12.3268 0.599732C12.0428 0.599632 11.7703 0.712313 11.5694 0.912986L6.99926 5.48267L2.42806 0.915118C2.22741 0.714585 1.95528 0.601927 1.67152 0.601927C1.38776 0.601927 1.11563 0.714585 0.914985 0.915118C0.71434 1.11565 0.601617 1.38763 0.601617 1.67122C0.601617 1.95482 0.71434 2.2268 0.914985 2.42733L5.48512 6.99701L0.914985 11.5667C0.713633 11.7672 0.600233 12.0395 0.599733 12.3236C0.599233 12.6077 0.711673 12.8803 0.912319 13.0816C1.11296 13.2828 1.38538 13.3961 1.66964 13.3966C1.95389 13.3971 2.2267 13.2848 2.42806 13.0842L6.99819 8.51456L11.5694 13.0842C11.6689 13.1836 11.787 13.2624 11.9169 13.3162C12.0469 13.3699 12.1862 13.3975 12.3268 13.3975C12.4675 13.3974 12.6067 13.3697 12.7367 13.3159C12.8666 13.262 12.9846 13.1831 13.0841 13.0837C13.1835 12.9843 13.2623 12.8662 13.3161 12.7364C13.3699 12.6065 13.3975 12.4673 13.3975 12.3267C13.3974 12.1861 13.3697 12.0469 13.3158 11.9171C13.262 11.7872 13.183 11.6693 13.0835 11.5699L8.51339 6.99915Z" fill="#595959"/>
      </svg>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user:{
        account: '',
        password: '',
        confirm:true
      },
      userInfo: {
        token: '',
      }
    }
  },
  methods: {
    submitForm() {
      fetch('https://api.hiskio.com/v2/auth/login', {
        method: 'POST',
        headers: {
          'accept': 'application/json',
          'content-type': 'application/json'
        },
        body: JSON.stringify(this.user),
      })
      .then(response => response.json())
      .then(data => {
        console.log(data);
        document.cookie = `Token=${data.access_token} ;max-age=${data.expires_in}`;
        this.userInfo.token = document.cookie;
        console.log(this.userInfo.token);
        this.$emit('close-modal')
        this.$emit('logged-in')
      })
    }
  },
}
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  background-color: #000000da;
  z-index: 1;
}

.modal {
  text-align: center;
  background-color: white;
  height: 500px;
  width: 500px;
  margin-top: 10%;
  padding: 60px 0;
  border-radius: 20px;
}
.close {
  margin: 10% 0 0 16px;
  cursor: pointer;
}

.close-img {
  width: 25px;
}


button {
  width: 150px;
  height: 40px;
  font-size: 14px;
  border-radius: 16px;
  margin-top: 50px;
}
</style>