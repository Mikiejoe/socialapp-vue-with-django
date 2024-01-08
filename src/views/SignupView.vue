<template>
    <div class="max-w-7xl mx-auto grid grid-cols-2 gap-4">
        <div class="main-left">
            <div class="p-12 bg-white border border-gray-200 rounded-lg">
                <h1 class="mb-6 text-2xl">Sign Up</h1>
                <p class="mb-6 text-gray-500">
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Cupiditate, nobis eius eos nesciunt nam a,
                    aliquam ducimus quasi corporis laboriosam tempora ipsa necessitatibus eligendi voluptates ad enim sed
                    error voluptatibus.
                </p>
                <p class="font-bold">
                    Already have an account? <RouterLink to="/login" class="underline">Login</RouterLink>
                </p>
            </div>
        </div>
        <div class="main-right">
            <div class="p-12 bg-white border border-gray-200 rounded-lg">
                <form class="space-y-6" v-on:submit.prevent="submitForm">
                    <div>
                        <label for="Fullname">Fullname</label><br>
                        <input type="text" v-model="form.name" class="w-full mt-2 py-3 px-6 border border-gray-200 rounded-lg"
                            placeholder="Full name" id="Fullname">
                    </div>
                    <div>
                        <label for="email">Email</label><br>
                        <input type="email" v-model="form.email" class="w-full mt-2 py-3 px-6 border border-gray-200 rounded-lg"
                            placeholder="Email" id="email">
                    </div>
                    <div>
                        <label for="password">Password</label><br>
                        <input type="password" v-model="form.password1" class="w-full mt-2 py-3 px-6 border border-gray-200 rounded-lg" id="password"
                            placeholder="Password">
                    </div>
                    <div>
                        <label for="cpassword">Confirm Password</label><br>
                        <input type="password" v-model="form.password2" class="w-full mt-2 py-3 px-6 border border-gray-200 rounded-lg"
                            placeholder="Confirm Password" id="cpassword">
                    </div>
                    <template v-if="errors.length>0">
                        <div class="text-white bg-red-300 p-2 rounded-lg">
                            <p v-for="error in errors" v-bind:key="error">{{ error }}</p>
                        </div>
                    </template>
                    <div>
                        <button class="py-2 px-6 bg-cyan-600 text-white rounded-lg">Sign Up</button>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import { useToastStore } from '@/stores/toast';

export default {
    setup() {
        const toastStore = useToastStore()

        return {
            toastStore
        }
    },

    data() {
        return {
            form: {
                email: '',
                name: '',
                password1: '',
                password2: '',

            },
            errors:[]
        }
    },
    methods:{
        submitForm(){
            this.errors = []
            if(this.form.name === ''){
                this.errors.push('name is required')
            }
            if(this.form.email === ''){
                this.errors.push('email is required')
            }
            if(this.form.password1 === ''){
                this.errors.push('password is required')
            }
            if(this.form.password1 !== this.form.password2){
                this.errors.push('password dont match')
            }

            if(this.errors.length === 0){
                axios.post('/api/account/signup/',this.form)
                .then(response=>{
                    if(response.data.message === 'success'){
                        this.toastStore.showToast(5000,'User registered successfully Login','bg-emerald-500')
                        this.form.email = ''
                        this.form.name = ''
                        this.form.password1 = ''
                        this.form.password2 = ''
                        console.log(response.data.message)

                    }else{
                        this.toastStore.showToast(5000,'Something went wrong!!','bg-red-400')
                       
                    }
                })
                .catch(error=>{
                    console.log(error)
                })
            }
        }
    }

}
</script>