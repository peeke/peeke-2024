<script setup>
import {useInterval} from '@vueuse/core'

const counter = useInterval(1000)
</script>

<template>
    <main>
        <slot />
        <aside>{{ counter }}</aside>
    </main>
</template>
