<template>
  <div class="relative flex items-top justify-center min-h-screen bg-gray-100 sm:items-center sm:pt-0">
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.1.2/dist/tailwind.min.css" rel="stylesheet">
    <div class="max-w-4xl mx-auto sm:px-6 lg:px-8">
      <div class="max-w-sm rounded overflow-hidden shadow-lg" v-for="(lecture,index) in lectures" :key="lecture.id">
        <div class="w-full card-img">
          <div class="flex">
            <svg width="18" height="23" viewBox="0 0 18 23" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M15.199 0.00015751H2.53353C1.87282 -0.00694167 1.23628 0.248359 0.763589 0.710039C0.290898 1.17172 0.0206656 1.80206 0.0121913 2.46276L0 22.1658L8.86624 18.4719L17.7325 22.1658V2.46276C17.7211 1.80087 17.4483 1.17037 16.9736 0.708964C16.4989 0.24756 15.8609 -0.0072599 15.199 0.00015751ZM15.199 18.4719L8.86624 15.7865L2.53353 18.4719V2.46276H15.199V18.4719Z" fill="white"/>
            </svg>
            <button @click="addToCart">
            <svg width="25" height="23" viewBox="0 0 25 23" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M22.387 13.0445L24.3885 4.03968C24.4239 3.8893 24.425 3.7329 24.3919 3.58202C24.3588 3.43113 24.2922 3.2896 24.1971 3.16784C24.1021 3.04608 23.9809 2.94719 23.8426 2.87846C23.7042 2.80973 23.5522 2.77291 23.3977 2.7707H6.77354L6.38343 0.83121C6.33925 0.598537 6.21563 0.388434 6.03369 0.236819C5.85175 0.0852046 5.6228 0.00149445 5.38597 0L1.04817 0C0.913152 0.00144694 0.779748 0.0294931 0.655581 0.0825349C0.531415 0.135577 0.418921 0.212573 0.324534 0.309123C0.230146 0.405672 0.155716 0.519879 0.105499 0.645215C0.0552813 0.77055 0.0302624 0.904555 0.0318724 1.03957V1.73224C0.0304091 1.86716 0.0555364 2.00105 0.105819 2.12625C0.156102 2.25146 0.230556 2.36554 0.324929 2.46197C0.419302 2.5584 0.531746 2.6353 0.65584 2.68827C0.779933 2.74124 0.913246 2.76925 1.04817 2.7707H4.00617L6.97968 17.6383C6.61524 17.8554 6.31375 18.1638 6.105 18.5331C5.89625 18.9024 5.78746 19.3198 5.78939 19.744C5.78939 20.0553 5.85071 20.3636 5.96984 20.6512C6.08897 20.9388 6.26359 21.2002 6.48372 21.4203C6.70386 21.6404 6.96519 21.815 7.25281 21.9342C7.54042 22.0533 7.84869 22.1146 8.16 22.1146C8.47131 22.1146 8.77958 22.0533 9.06719 21.9342C9.35481 21.815 9.61614 21.6404 9.83627 21.4203C10.0564 21.2002 10.231 20.9388 10.3502 20.6512C10.4693 20.3636 10.5306 20.0553 10.5306 19.744C10.5322 19.4222 10.47 19.1032 10.3477 18.8055C10.2254 18.5078 10.0454 18.2373 9.81799 18.0096H18.692C18.4653 18.2371 18.2856 18.5071 18.1633 18.8042C18.0411 19.1012 17.9785 19.4195 17.9794 19.7407C17.9794 20.052 18.0407 20.3603 18.1598 20.6479C18.2789 20.9355 18.4536 21.1968 18.6737 21.417C18.8938 21.6371 19.1552 21.8117 19.4428 21.9308C19.7304 22.05 20.0387 22.1113 20.35 22.1113C20.6613 22.1113 20.9696 22.05 21.2572 21.9308C21.5448 21.8117 21.8061 21.6371 22.0262 21.417C22.2464 21.1968 22.421 20.9355 22.5401 20.6479C22.6593 20.3603 22.7206 20.052 22.7206 19.7407C22.7229 19.2886 22.599 18.8449 22.3629 18.4593C22.1268 18.0738 21.7878 17.7618 21.384 17.5585L21.6178 16.5078C21.6532 16.3574 21.6543 16.2011 21.6212 16.0502C21.5881 15.8993 21.5215 15.7578 21.4264 15.636C21.3314 15.5142 21.2102 15.4153 21.0719 15.3466C20.9335 15.2779 20.7815 15.2411 20.627 15.2389H9.26495L8.98788 13.8535H21.4006C21.6325 13.8507 21.8565 13.7691 22.0358 13.6221C22.2151 13.475 22.3389 13.2713 22.387 13.0445Z" fill="white"/>
            </svg>
            </button>
          </div>
        </div>
        <div class="px-6 py-4">
          <div class="font-bold text-xl mb-2">{{ lecture.title }}</div>
          <div class="flex">
            <div>
              <svg width="39" height="39" viewBox="0 0 39 39" fill="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
<path d="M19.2437 38.1891C29.5306 38.1891 37.8698 29.8499 37.8698 19.563C37.8698 9.27615 29.5306 0.936981 19.2437 0.936981C8.95684 0.936981 0.617676 9.27615 0.617676 19.563C0.617676 29.8499 8.95684 38.1891 19.2437 38.1891Z" fill="#C4C4C4"/>
<path d="M19.2437 38.1891C29.5306 38.1891 37.8698 29.8499 37.8698 19.563C37.8698 9.27615 29.5306 0.936981 19.2437 0.936981C8.95684 0.936981 0.617676 9.27615 0.617676 19.563C0.617676 29.8499 8.95684 38.1891 19.2437 38.1891Z" fill="url(#pattern0)"/>
<path d="M19.2437 38.1891C29.5306 38.1891 37.8698 29.8499 37.8698 19.563C37.8698 9.27615 29.5306 0.936981 19.2437 0.936981C8.95684 0.936981 0.617676 9.27615 0.617676 19.563C0.617676 29.8499 8.95684 38.1891 19.2437 38.1891Z" stroke="white"/>
<defs>
<pattern id="pattern0" patternContentUnits="objectBoundingBox" width="1" height="1">
<use xlink:href="#image0_147_477" transform="translate(0 -0.256098) scale(0.0243902)"/>
</pattern>
<image id="image0_147_477" width="41" height="62" xlink:href="data:image/jpeg;base64,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"/>
</defs>
              </svg>
            </div>
            <div class="lecturer" v-for="teacher in lecture.lecturers" :key="teacher.id">
              {{ teacher.username }}
            </div>
          </div>
          <div class="flex justify-between text-gray-700 text-base">
            <span>剩3天</span>
            <span>已募資{{ getProgress(index) }}%</span>
          </div>
          <div class="mb-1 text-base font-medium text-red-700 dark:text-red-500"></div>
          <div class="w-full bg-gray-200 rounded-full h-2.5 mb-4 dark:bg-gray-700">
            <div class="bg-red-600 h-2.5 rounded-full dark:bg-red-500" :style="{ 'width': getProgress(index)+'%'}"></div>
          </div>
        </div>
        <div class="flex px-6 pt-4 pb-2">
          <span class="inline-block rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">NT$ {{ lecture.price }}</span>
          <span class="inline-block gray-200 px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">NT$ {{ lecture.fixed_price }}</span>
          <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#winter</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lectures: [],
      test:'',
    }
  },
  beforeCreate() {
    fetch('https://api.hiskio.com/v2/courses/fundraising')
        .then(res => {return res.json()})
        .then(arr => {this.lectures = arr})
  },
  methods: {
    addToCart() {
      
    },
    getProgress(index) {
      return (Math.round(this.lectures[index].consumers/this.lectures[index].students*100))
    }
  },
}
</script>


<style>
.card-img {
  width: 280px;
  height: 153px;
  background-image: url('../assets/lecture.jpg');
  background-repeat: no-repeat;
}
</style>