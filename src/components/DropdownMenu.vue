<script setup>
import { ref } from 'vue'
import { UserIcon, UserMinusIcon } from '@heroicons/vue/24/outline'

const show = ref(false)

const toggle = () => {
  show.value = !show.value
}

</script>

<template>
  <div class="relative">
    <img
      src="../assets/avatar.jpg"
      class="rounded-full w-10 h-10 cursor-pointer"
      @click="toggle"
    />
    <transition
      enter-active-class="transition-opacity duration-300"
      enter-from-class="opacity-0"
      leave-active-class="transition-opacity duration-300"
      leave-to-class="opacity-0"
    >
      <div
        class="absolute top-16 right-0 z-10 w-40 py-2 bg-white rounded-sm shadow"
        v-show="show"
      >
        <ul>
          <li class="text-gray-700 hover:bg-blue-100 hover:text-blue-600 p-2">
            <router-link to="/profile" class="flex items-center space-x-2">
              <UserIcon class="w-5 h-5" />
              <span class="text-sm font-bold">プロファイル</span>
            </router-link>
          </li>
          <li class="text-gray-700 hover:bg-blue-100 hover:text-blue-600 p-2">
            <a href="/#" class="flex items-center space-x-2">
              <UserMinusIcon class="w-5 h-5" />
              <span class="text-sm font-bold">ログアウト</span></a
            >
          </li>
        </ul>
      </div>
    </transition>
  </div>
</template>
