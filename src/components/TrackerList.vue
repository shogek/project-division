<script setup lang="ts">
import TrackerItem from './TrackerItem.vue'
import SectionHeader from './SectionHeader.vue'
</script>

<template>
<div class="tracker-list-wrapper">
    <SectionHeader label="Trackers" />

    <div class="trackers">
        <TrackerItem
            name="Capulus"
            iconName="coffee"
            :currentProgress="2"
            :totalProgress="2"
        />

        <TrackerItem
            name="Dulcis"
            iconName="candy"
            :currentProgress="50"
            :totalProgress="70"
        />

        <TrackerItem
            name="Tenebris"
            iconName="chocos"
            :currentProgress="0"
            :totalProgress="2"
        />

        <TrackerItem
            name="Voluptas"
            iconName="pleasure"
            :currentProgress="0"
            :totalProgress="0"
        />
    </div>
</div>
</template>

<style>
.tracker-list-wrapper {
    display: flex;
    flex-direction: column;
}

.tracker-list-wrapper .trackers {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: var(--gap-small);
}
</style>
