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
            :sets="4"
            :total="75"
            :max="36"
        />

        <ExcerciseItem
            iconName="cardio"
            name="Jumping jacks"
            :sets="2"
            :total="450"
            :max="250"
        />

        <ExcerciseItem
            iconName="push-up"
            name="High push ups"
            :sets="3"
            :total="82"
            :max="35"
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
