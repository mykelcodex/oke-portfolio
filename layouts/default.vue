<template>
  <div class="bg-purple">
    <div class="max-w-screen-xl w-full mx-auto">
      <div class="bg-top bg-no-repeat background-size font-sans flex flex-col min-h-screen" :style="{ backgroundImage: `url(${backgroundUrl})`}">
      <div class="px-6 sm:px-10 lg:px-20 xl:px-32 pt-10 pb-5 lg:py-10">
        <div class="flex items-center justify-between">
          <nuxt-link to="/"><img :src="logo" class="w-10 lg:w-12" alt="Oke Michael"/></nuxt-link>
          <div>
            <ul class="flex items-center">
              <nuxt-link to="/blog"><li :class="this.$route.path == '/blog' ? 'bg-yellow text-white' : 'text-light-purple'" class="font-bold text-sm md:text-base lg:text-lg border-2 px-3 md:px-6 py-1 rounded hover:bg-yellow border-yellow active:text-white hover:text-white transition duration-500 ease-in-out">Blog</li></nuxt-link>
            </ul>
          </div>
        </div>
      </div>
      <transition name="page" mode="out-in">
        <nuxt/>
      </transition>
    </div>
    </div>
  </div>
</template>

<script>

import backgroundUrl from '~/assets/images/background.svg'
import logo from '~/assets/images/mike.svg'
export default {
  
  data(){
    return { 
      backgroundUrl,
      logo
    }
  },
  
}
</script>
<style lang="scss">
.page-enter-active, .page-leave-active {
  transition: opacity 1s, transform 0.5s;
}
.page-enter, .page-leave-to {
  opacity: 0;
  transform: translateX(-30%);
}
</style>
