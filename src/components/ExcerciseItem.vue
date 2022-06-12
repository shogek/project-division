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
    <div class="excercise-item-wrapper corner-border-2 corner-border-3">
        <div class="border">
            <div class="title-row corner-1 corner-4">
                <div class="icon">
                    <CustomIcon :iconName="iconName" />
                </div>
                <h4 class="title corner-1 corner-4">{{ name }}</h4>
            </div>
            <div class="stats-row">
                <div class="vertical corner-4">
                    <p>Sets</p>
                    <p>{{ sets }}</p>
                </div>

                <div class="vertical corner-1 corner-4">
                    <p>Total</p>
                    <p>{{ total }}</p>
                </div>

                <!-- TODO: Fix missing upper-right corner -->
                <div class="vertical corner-1 corner-4">
                    <p>Max</p>
                    <p>{{ max }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style>


.excercise-item-wrapper {
    display: flex;
    flex-direction: column;
}

.excercise-item-wrapper .border {
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
