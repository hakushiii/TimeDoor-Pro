<script setup>
    import BaseInput from '../ui/BaseInput.vue';
    import BaseButton from '../ui/BaseButton.vue';
</script>

<template>
    <div class="container-fluid py-5" style="background-color: #f5f5f5">
        <div style="background-color: #ffffff" class="p-5 m-auto signup-form">
            <div class="text-center">
                <img src="../../assets/images/Logo.png" alt="Logo" />
                <h2 class="mt-4">Create your account</h2>
                <p>Enter your details to use all the app features.</p>
            </div>
            <form class="mt-3">
                <div class="row">
                    <div class="col-md-6"><!-- Firstname -->
                        <BaseInput
                        type="text"
                        identiy="username"
                        placeholder="Ex: Juan"
                        label="First Name"/>
                    </div>
                    <div class="col-md-6"><!-- Lastname -->
                        <BaseInput
                        type="text"
                        identiy="username"
                        placeholder="Ex: Carlos"
                        label="Last Name"/>
                    </div>
                </div>
                <div class="my-4"><!-- Username -->
                    <BaseInput
                        type="text"
                        identiy="username"
                        placeholder="Ex: timedoorstudent"
                        label="Username"/>
                </div>
                <div class="my-4"><!-- Email -->
                    <BaseInput
                        type="email"
                        identiy="email"
                        placeholder="Ex: student@timedoor.com"
                        label="Email"/>
                </div>
                <div class="my-4"><!-- Password -->
                    <BaseInput
                        type="password"
                        identiy="password"
                        placeholder="*********"
                        label="Password"/>
                </div>
                <div class="my-4"><!-- Confirm Password -->
                    <BaseInput
                        type="password"
                        identiy="confirmPassword"
                        placeholder="*********"
                        label="Confirm Password"/>
                </div>
                <div class="my-4">
                    <base-input type="file" identity="recipeImage"
                    label="Profile Photo" isImage="true">
                    <div>
                        <div class="border p-1 mt-2 rounded-circle" >
                            <img src="../../assets/images/user.png"
                            class="rounded-circle"
                            width="140" height="150" style="object-fit:
                            cover"/>
                        </div>
                        <div class="text-center"
                        style="transform: translateY(-24px)" >
                            <i class="fa-solid fa-camera fs-5 p-2
                            rounded-circle bg-white" ></i>
                        </div>
                    </div>
                    </base-input>
                </div>
                <BaseButton class="login w-100 my-3">Register</BaseButton>
            </form>
            <div class="text-center mt-4">
              <p class="fw-semibold">
                Already have account?<span style="color: #4c4ddc">
                    <RouterLink to="/login" class="text-decoration-none"> Login</RouterLink></span>
              </p>
            </div>
        </div>
    </div>
</template>