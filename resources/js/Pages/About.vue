<script setup>
defineProps({
    user: String
})
</script>
<template>
    <Head title=" | About">
        <meta head-key="description" name="description" content="This is about page."/>
    </Head>
    <h1>
        About page {{ user }}
    </h1>
</template>
