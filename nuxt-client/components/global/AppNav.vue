<template>
    <div class="flex justify-between mb-10">
        <ul class="flex item-center">
            <li class="mr-4">
                <nuxt-link :to="{name: 'index'}" class="text-gray-800 font-medium">
                Home
            </nuxt-link>
            </li>
        </ul>
        <ul class="flex items-center">
            <template v-if="$auth.loggedIn">
                <li class="mr-4">
                <nuxt-link :to="{name: 'account'}" class="text-gray-800 font-medium">
                {{ $auth.user.name }}
            </nuxt-link>
            </li>
            <li class="mr-4">
                <a href="#" class="text-gray-800 font-medium">
                Singout
            </a>
            </li>
            </template>
            <template v-else>
                <li class="mr-4">
                <nuxt-link :to="{name: 'auth-signin'}" class="text-gray-800 font-medium">
                Sign in
            </nuxt-link>
            </li>
            <li class="mr-4">
                <a href="#" class="text-gray-800 font-medium">
                Sign up
            </a>
            </li>
            </template>
        </ul>
    </div>
</template>

<script>
export default {
    
}
</script>