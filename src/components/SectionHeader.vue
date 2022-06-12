<script setup lang="ts">
defineProps<{
    label: string
}>()
</script>

<template>
<h2 class="section-header">
    {{ label }}
</h2>
</template>

<style>
.section-header {
    font-size: 2.4em;
    display: grid;
    place-items: center;
    margin-top: var(--gap-larger);
    margin-bottom: var(--gap-small);
    padding: var(--gap-medium);
    border: var(--app-border);
    border-left: none;
    border-right: none;
}
</style>