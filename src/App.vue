
<template>
  <nav class="py-5 px-8 border-b border-grey-20">
    <div class="max-w-7xl mx-auto">
      <div class="flex item-center justify-between">
        <div class="menu-left">
          <a href="#" class="text-xl">Mike</a>
        </div>
        <div class="menu-center  flex space-x-12">
          <RouterLink to="/feed" class="text-purple-700">
            Home
          </RouterLink>
          <RouterLink to="/messages" class="text-purple-700">
            Messages
          </RouterLink>
          <RouterLink to="#" class="text-purple-700">
            Notifications
          </RouterLink>
          <RouterLink to="#" class="text-purple-700">
            Search
          </RouterLink>
          
        </div>
        <div class="menu-right">
          <a href="#" class="rounded-full border-gray-300">
            <img src="./assets/logo.svg" style="height: 30px; width:30px;" alt="">
          </a>
        </div>
      </div>
      

    </div>
  </nav>
  <main class="px-8 py-6 bg-gray-100">
    <RouterView />
  </main>
</template>

