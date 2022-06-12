<script setup lang="ts">
import CustomIcon from './CustomIcon.vue'
import CornerWrapper from './CornerWrapper.vue'

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
<div class="tracker-item-wrapper corners">
    <CornerWrapper>
        <div class="content">
            <h3 class="name">{{ name }}</h3>
            <div class="icon">
                <CustomIcon :iconName="iconName" />
            </div>
            <div class="progress">
                {{ currentProgress }} / {{ totalProgress }}
            </div>
        </div>
    </CornerWrapper>
</div>
</template>

<style>
.tracker-item-wrapper {
    width: calc(50% - (var(--gap-small) / 2));
}

.content {
    border: var(--app-border);
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: var(--gap-medium);
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
