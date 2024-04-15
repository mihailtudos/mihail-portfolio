<script setup lang="ts">
const route = useRoute()

const links = [
    [{
        label: 'Home',
        icon: 'i-heroicons-home',
        to: '/getting-started/installation'
    }, {
        label: 'Blogs',
        icon: 'i-heroicons-chart-bar',
        to: `${route.path.startsWith('/dev') ? '/dev' : ''}/components/horizontal-navigation`
    }, ], [{
        label: 'About',
        icon: 'i-heroicons-light-bulb'
    }, {
        label: 'Contact',
        icon: 'i-heroicons-question-mark-circle'
    }]
]
</script>

<template>
    <UHorizontalNavigation :links="links" class="border-b py-2 border-gray-200 dark:border-gray-800" />
</template>

