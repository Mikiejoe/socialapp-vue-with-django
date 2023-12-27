<template>
    <div class="max-w-7xl mx-auto grid grid-cols-2 gap-4">
     <div class="main-left">
         <div class="p-12 bg-white border border-gray-200 rounded-lg">
             <h1 class="mb-6 text-2xl">Login </h1>
             <p class="mb-6 text-gray-500">
                 Lorem ipsum dolor, sit amet consectetur adipisicing elit. Cupiditate, nobis eius eos nesciunt nam a, aliquam ducimus quasi corporis laboriosam tempora ipsa necessitatibus eligendi voluptates ad enim sed error voluptatibus.
             </p>
             <p class="font-bold">
                 Don't have an account? <RouterLink to="/signup" class="underline">SignUp</RouterLink>
             </p>
         </div>
     </div>
     <div class="main-right">
         <div class="p-12 bg-white border border-gray-200 rounded-lg">
             <form class="space-y-6">
                 
                 <div>
                     <label for="email">Email</label><br>
                     <input type="email" class="w-full mt-2 py-3 px-6 border border-gray-200 rounded-lg" name="email" id="email" placeholder="Email" autocomplete="email">
                 </div>
                 <div>
                     <label for="password">Password</label><br>
                     <input type="password" class="w-full mt-2 py-3 px-6 border border-gray-200 rounded-lg" name="password" id="password" placeholder="Password">
                 </div>
                 
                 <div>
                     <button class="py-2 px-6 bg-cyan-600 text-white rounded-lg">Login</button>
                 </div>
             </form>
         </div>
     </div>
    </div>
 </template>