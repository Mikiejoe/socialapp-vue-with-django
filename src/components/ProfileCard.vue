<template>
    <div class="p-4 bg-white border border-gray-200 text-center rounded-lg">
        <img src="../assets/images/-5938306102703799598_121.jpg" alt="" class="mb-6 w-[180px] h-[180px] rounded-full">

        <p><strong>{{ userStore.user.name }}</strong></p>

        <div class="mt-6 flex space-x-8 justify-around">
            <p class="text-xs text-gray-500">12 friends</p>
            <p class="text-xs text-gray-500">1 posts</p>
        </div>
    </div>
</template>

<script>
import { useUserStore } from '@/stores/user.js'
export default {
    setup() {
        const userStore = useUserStore()
        return {
            userStore
        }
    },
}
</script>