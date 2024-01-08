<template>
  <nav class="py-5 px-8 border-b border-grey-20">
    <div class="max-w-7xl mx-auto">
      <div class="flex item-center justify-between">
        <div class="menu-left">
          <a href="#" class="text-xl">Mike</a>
        </div>
        <div class="menu-center  flex space-x-12" v-if="userStore.user.isAuthenticated">
          <RouterLink to="/feed" class="text-purple-700">
            Home
          </RouterLink>
          <RouterLink to="/messages" class="text-purple-700">
            Messages
          </RouterLink>
          <RouterLink to="#" class="text-purple-700">
            Notifications
          </RouterLink>
          <RouterLink to="/search" class="text-purple-700">
            Search
          </RouterLink>

        </div>
        <div class="menu-right">
          <template v-if="userStore.user.isAuthenticated">
            <a href="#" class="rounded-full border-gray-300">
              <img src="./assets/logo.svg" style="height: 30px; width:30px;" alt="">
            </a>
          </template>
          <template v-else>
            <RouterLink to="/login" class="py-4 px-6 bg-gray-600 text-white rounded-lg">Login</RouterLink>
            <RouterLink to="/signup" class="py-4 px-6 bg-purple-600 ml-2 text-white rounded-lg">Sign up</RouterLink>
          </template>
        </div>
      </div>


    </div>
  </nav>
  <main class="px-8 py-6 bg-gray-100">
    <RouterView />
  </main>
  <Toast />
</template>

<script>
import axios from 'axios'
import Toast from '@/components/Toast.vue';
import { useUserStore } from '@/stores/user.js'

export default {
  setup() {
    const userStore = useUserStore()
    return {
      userStore
    }
  },
  components: {
    Toast
  },
  beforeCreate() {
    this.userStore.initStore()
    const token = this.userStore.user.access

    if (token) {
      axios.defaults.headers.common['Authorization'] = 'Bearer ' + token
    } else {
      axios.defaults.headers.common['Authorization'] = ''

    }
  }
}
</script>

