<template>
    <div class="max-w-7xl mx-auto grid grid-cols-4 gap-4">
        <div class="main-left col-span-1">
            <ProfileCard />
        </div>
        <div class="main-center col-span-2 space-y-4">
            <div class="bg-white border border-gray-200 rounded-lg">
                <div class="p-4">
                    <textarea name="text" id="text" class="p-4 w-full bg-gray-100 rounded-lg"
                        placeholder="Wht's up??"></textarea>
                </div>
                <div class="p-4 border-t border-gray flex justify-between">
                    <a href="#" class="inline-block py-2 px-6 bg-gray-600 text-white rounded-lg">Attach Image</a>
                    <a href="#" class="inline-block py-2 px-6 bg-purple-600 text-white rounded-lg">Post</a>
                </div>
            </div>

            <div class="p-4 bg-white border border-gray-200 rounded-lg">
                <div class="flex items-center justify-between">
                    <div class="flex items-center space-x-6">
                        <img src="../assets/images/-5938306102703799598_121.jpg" alt=""
                            class="w-[40px] h-[40px] rounded-full">
                        <p><strong>mike</strong></p>
                    </div>
                    <p class="text-gray-600">12 minutes ago</p>
                </div>
                <img src="../assets/images/-5938306102703799598_121.jpg" style=" width:600px;height:300px" alt=""
                    class="rounded-md mt-4">
                <div class="my-6 flex justify-between">
                    <div class="flex space-x-6">
                        <div class="flex items-center space-x-2">
                            <p class="text-gray-500 text-xs">12 likes</p>

                        </div>
                        <div class="flex items-center space-x-2">
                            <p class="text-gray-500 text-xs">12 comments</p>

                        </div>
                    </div>
                    <div>
                        <p class="text-gray-500 text-xs">more</p>
                    </div>
                </div>
            </div>

            <div class="p-4 bg-white border border-gray-200 rounded-lg">
                <div class="flex items-center justify-between">
                    <div class="flex items-center space-x-6">
                        <img src="../assets/images/-5938306102703799598_121.jpg" alt=""
                            class="w-[40px] h-[40px] rounded-full">
                        <p><strong>Mikeeljo</strong></p>
                    </div>
                    <p class="text-gray-600">12 minutes ago</p>
                </div>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Deserunt vitae cum asperiores laudantium
                    repudiandae sit illum possimus illo tempore dolores.</p>
                <div class="my-6 flex justify-between">
                    <div class="flex space-x-6">
                        <div class="flex items-center space-x-2">
                            <p class="text-gray-500 text-xs">12 likes</p>

                        </div>
                        <div class="flex items-center space-x-2">
                            <p class="text-gray-500 text-xs">12 comments</p>

                        </div>
                    </div>
                    <div>
                        <p class="text-gray-500 text-xs">more</p>
                    </div>
                </div>
            </div>

        </div>
        <div class="main-right cols-span-1 space-y-4">
            <PeopleYouMayKnow>

            </PeopleYouMayKnow>
            <Trends />
        </div>
    </div>
</template>

<script>
import PeopleYouMayKnow from '../components/PeopleYouMayKnow.vue';
import Trends from '../components/Trends.vue';
import ProfileCard from '../components/ProfileCard.vue';
import { useUserStore } from '@/stores/user.js'
export default {
    setup() {
        const userStore = useUserStore()
        return {
            userStore
        }
    },
    name: 'Feed',
    components: {
        PeopleYouMayKnow,
        Trends,
        ProfileCard
    }
}
</script>