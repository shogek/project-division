<script setup lang="ts">
import CustomIcon from './CustomIcon.vue'
import CornerWrapper from './CornerWrapper.vue'

defineProps<{
    iconName: string
    title: string
    explanation: string
    progress: number
}>()
</script>

<template>
<div class="badge-item-wrapper">
    <!-- <CornerWrapper> -->
        <!-- <div class="content"> -->
            <div class="icon-column">
                <CustomIcon :iconName="iconName" />
            </div>
            <div class="text-row">
                <h2 class="title">{{ title }}</h2>
                <p class="explanation">{{ explanation }}</p>
            </div>
            <p class="progress">{{ progress }}%</p>
        <!-- </div> -->
    <!-- </CornerWrapper> -->
</div>
</template>

<style>

.badge-item-wrapper {
    display: flex;
    flex-direction: row;
    height: var(--badge-card-height);
}

.badge-item-wrapper .content {
    
}

.badge-item-wrapper .icon-column {
    display: grid;
    place-items: center;
    padding: var(--gap-medium);
    border: var(--app-border);
}

.badge-item-wrapper .icon-column svg {
    height: var(--badge-icon-height);
    width: var(--badge-icon-height);
}

.badge-item-wrapper .text-row {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: var(--gap-medium);
    gap: var(--gap-smaller);
    border: var(--app-border);
    border-left: none;
    flex-grow: 1;
}

.badge-item-wrapper .text-row .title {
    font-size: 1.2em;
    font-weight: bold;
}

.badge-item-wrapper .text-row .explanation {
    font-size: 0.8em;
    color: var(--font-color-weaker);
}

.badge-item-wrapper .progress {
    display: grid;
    place-items: center;
    color: var(--font-color-weaker);
    border: var(--app-border);
    border-left: none;
    font-size: 1.4em;
    width: var(--badge-card-height);
}
</style>
