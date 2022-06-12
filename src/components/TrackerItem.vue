<script setup lang="ts">
import CustomIcon from './CustomIcon.vue'

defineProps<{
    /** TODO: Explaine me */
    name: string
    /** TODO: Explaine me */
    iconName: string
    /** TODO: Explaine me */
    currentProgress: number
    /** TODO: Explaine me */
    // TODO: Rename me
    totalProgress: number
}>()
</script>

<template>
    <div class="tracker-item-wrapper corner-border-2 corner-border-3">
        <div class="content corner-1 corner-4">
            <h3 class="name">{{ name }}</h3>

            <div class="icon">
                <CustomIcon :iconName="iconName" />
            </div>

            <div class="progress">
                {{ currentProgress }} / {{ totalProgress }}
            </div>
        </div>
    </div>
</template>

<style>
.tracker-item-wrapper {
    width: calc(50% - (var(--gap-small) / 2));
}

.content {
    border: var(--app-border);
    padding: var(--gap-medium);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: var(--gap-larger);
}

.tracker-item-wrapper .name {
    font-size: 1.8em;
    font-weight: bold;
}

.tracker-item-wrapper .icon svg {
    height: var(--tracker-icon-height);
}
</style>
