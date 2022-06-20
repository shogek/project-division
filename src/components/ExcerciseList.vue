<script setup lang="ts">
import ExcerciseItem from './ExcerciseItem.vue'
import SectionHeader from './SectionHeader.vue'
</script>

<template>
<div class="excercise-list-wrapper">
    <SectionHeader label="Excercises" />

    <div class="excercises">
        <ExcerciseItem
            iconName="pull-up"
            name="Neutral grip pull-ups"
            :sets="[3017, 33, 12]"
        />

        <ExcerciseItem
            iconName="cardio"
            name="Jumping jacks"
            :sets="[37, 33, 12]"
        />

        <ExcerciseItem
            iconName="push-up"
            name="High push ups"
            :sets="[37, 33, 12]"
        />
    </div>
</div>
</template>

<style>
.excercise-list-wrapper {
    display: flex;
    flex-direction: column;
}

.excercise-list-wrapper .excercises {
    display: flex;
    flex-direction: column;
    gap: var(--gap-small);
}
</style>
