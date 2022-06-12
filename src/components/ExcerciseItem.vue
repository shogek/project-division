<script setup lang="ts">
import CustomIcon from './CustomIcon.vue'

defineProps<{
    /** TODO: Explain me */
    iconName: string
    /** TODO: Explain me */
    name: string
    /** TODO: Explain me */
    sets: number
    /** TODO: Explain me */
    total: number
    /** TODO: Explain me */
    max: number
}>()
</script>

<template>
<div class="excercise-item-wrapper">
    <div class="title-row">
        <div class="icon">
            <CustomIcon :iconName="iconName" />
        </div>
        <h4 class="title">{{ name }}</h4>
    </div>
    <div class="stats-row">
        <div class="vertical">
            <p>Sets</p>
            <p>{{ sets }}</p>
        </div>

        <div class="vertical">
            <p>Total</p>
            <p>{{ total }}</p>
        </div>

        <div class="vertical">
            <p>Max</p>
            <p>{{ max }}</p>
        </div>
    </div>
</div>
</template>

<style>
.excercise-item-wrapper {
    display: flex;
    flex-direction: column;
    border: var(--app-border);
}

.excercise-item-wrapper .vertical {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    justify-content: center;
    align-items: center;
    gap: var(--gap-small);
    padding: var(--gap-medium);
    border: var(--app-border);
    border-left: none;
    border-top: none;
    border-bottom: none;
}

.excercise-item-wrapper .vertical:last-child {
    border-right: none;
}

.excercise-item-wrapper .title-row {
    display: flex;
    flex-direction: row;
    height: var(--excercise-card-height);
    border: var(--app-border);
    border-right: none;
    border-top: none;
    border-left: none;
}

.excercise-item-wrapper .title-row .icon {
    display: grid;
    place-items: center;
    padding: var(--gap-medium);
    border: var(--app-border);
    border-left: none;
    border-top: none;
    border-bottom: none;
}

.excercise-item-wrapper .icon svg {
    height: var(--excercise-icon-height);
}

.excercise-item-wrapper .title-row .title {
    display: flex;
    align-items: center;
    flex-grow: 1;
    font-size: 1.4em;
    padding: var(--gap-medium);
}

.excercise-item-wrapper .stats-row {
    display: flex;
    flex-direction: row;
}
</style>
