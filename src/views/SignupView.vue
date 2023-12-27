<template>
   <div class="max-w-7xl mx-auto grid grid-cols-2 gap-4">
    <div class="main-left">
        <div class="p-12 bg-white border border-gray-200 rounded-lg">
            <h1 class="mb-6 text-2xl">Sign Up</h1>
            <p class="mb-6 text-gray-500">
                Lorem ipsum dolor, sit amet consectetur adipisicing elit. Cupiditate, nobis eius eos nesciunt nam a, aliquam ducimus quasi corporis laboriosam tempora ipsa necessitatibus eligendi voluptates ad enim sed error voluptatibus.
            </p>
            <p class="font-bold">
                Already have an account? <RouterLink to="/login" class="underline">Login</RouterLink>
            </p>
        </div>
    </div>
    <div class="main-right">
        <div class="p-12 bg-white border border-gray-200 rounded-lg">
            <form class="space-y-6">
                <div>
                    <label for="Fullname">Fullname</label><br>
                    <input type="text" class="w-full mt-2 py-3 px-6 border border-gray-200 rounded-lg" placeholder="Full name">
                </div>
                <div>
                    <label for="email">Email</label><br>
                    <input type="email" class="w-full mt-2 py-3 px-6 border border-gray-200 rounded-lg" placeholder="Email">
                </div>
                <div>
                    <label for="password">Password</label><br>
                    <input type="password" class="w-full mt-2 py-3 px-6 border border-gray-200 rounded-lg" placeholder="Password">
                </div>
                <div>
                    <label for="cpassword">Confirm Password</label><br>
                    <input type="password" class="w-full mt-2 py-3 px-6 border border-gray-200 rounded-lg" placeholder="Confirm Password">
                </div>
                <div>
                    <button class="py-2 px-6 bg-cyan-600 text-white rounded-lg">Sign Up</button>
                </div>
            </form>
        </div>
    </div>
   </div>
</template>