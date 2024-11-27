<script setup>
    import { RouterLink } from 'vue-router';
    import BaseInput from '../ui/BaseInput.vue';
    import BaseButton from '../ui/BaseButton.vue';
    
    import { reactive } from 'vue';
    import { useStore } from 'vuex';
    import { useRouter } from 'vue-router';

    const store = useStore()
    const router = useRouter()

    const loginData = reactive({
        email: "",
        password: "",
        isLogin: true,
    })
    
    const login = async () => {
        await store.dispatch("auth/getLoginData", loginData)
        router.push("/")
    }
</script>

<template>
    <div class="container-fluid py-5" style="background-color: #f5f5f5;">
      <div style="background-color: #ffffff; width: 400px" class="p-5 m-auto login-form">
        <div class="text-center">
            <img src="../../assets/images/Logo.png" alt="Logo" />
            <h2 class="mt-4">Log in to your account</h2>
            <p>Welcome back! Please enter your details.</p>
        </div>
        <form @submit.prevent="login">
            <div class="my-4"><!-- Email -->
                <BaseInput
                    type="email"
                    identiy="email"
                    placeholder="Ex: student@timedoor.com"
                    label="Email"
                    v-model="loginData.email"/>
            </div>
            <div class="my-4"><!-- Password -->
              <BaseInput
                type="password"
                identiy="password"
                placeholder="*********"
                label="Password"
                v-model="loginData.password"/>
            </div>
            <BaseButton class="login w-100 my-3">Register</BaseButton>
        </form>
        <div class="text-center mt-4">
            <p class="fw-semibold">
                Don’t have an account?<span style="color: #4c4ddc">
                    <RouterLink to="/signup" class="text-decoration-none">
                        Signup</RouterLink></span>
            </p>
        </div>
      </div>
    </div>
  </template>