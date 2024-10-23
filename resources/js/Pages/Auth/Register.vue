<script setup>
import {useForm} from "@inertiajs/vue3";

const form = useForm({
    name: null,
    email: null,
    password: null,
    password_confirmation: null,
})

const submit = () => {
    form.post(route('register'), {
        onError: () => form.reset('password', 'password_confirmation')
    })
}
</script>
<template>
    <Head title="Register"/>
    <h1 class="title">
        Register a new account
    </h1>
    <div class="w-2\4 mx-auto">
        <form @submit.prevent="submit">
            <div class="mb-6">
                <label for="name">
                    Name
                </label>
                <input type="text" id="name" v-model="form.name"/>
                <small class="error">
                    {{ form.errors.name }}
                </small>
            </div>
            <div class="mb-6">
                <label for="email">
                    E-mail
                </label>
                <input type="email" id="email" v-model="form.email"/>
                <small class="error">
                    {{ form.errors.email }}
                </small>
            </div>
            <div class="mb-6">
                <label for="password">
                    Password
                </label>
                <input type="password" id="password" v-model="form.password"/>
                <small class="error">
                    {{ form.errors.password }}
                </small>
            </div>
            <div class="mb-6">
                <label for="password_confirmation">
                    Confirm Password
                </label>
                <input type="password" id="password_confirmation" v-model="form.password_confirmation"/>
            </div>
            <div>
                <p class="text-slate-600 mb-2">
                    Already a user? <a href="#" class="text-link">
                    Login
                </a>
                </p>
                <button class="primary-btn" :disabled="form.processing">
                    Register
                </button>
            </div>
        </form>
    </div>
</template>
