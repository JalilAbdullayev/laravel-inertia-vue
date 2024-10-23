<template>
    <div>
        <header>
            <nav>
                <Link :href="route('home')" class="nav-link" :class="{'bg-slate-700' : $page.component === 'Home'}">
                    Home
                </Link>
                <div class="space-x-6" v-if="$page.props.auth.user">
                    <Link :href="route('dashboard')" class="nav-link"
                          :class="{'bg-slate-700' : $page.component === 'Dashboard'}">
                        Dashboard
                    </Link>
                    <Link :href="route('logout')" method="post" as="button" type="button" class="nav-link">
                        Logout
                    </Link>
                </div>
                <div class="space-x-6" v-else>
                    <Link :href="route('register')" class="nav-link"
                          :class="{'bg-slate-700' : $page.component === 'Auth/Register'}">
                        Register
                    </Link>
                    <Link :href="route('login')" class="nav-link"
                          :class="{'bg-slate-700' : $page.component === 'Auth/Login'}">
                        Login
                    </Link>
                </div>
            </nav>
        </header>
        <main class="p-4">
            <slot/>
        </main>
    </div>
</template>
<script setup lang="ts">
</script>
