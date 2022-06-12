<script setup lang="ts">
import BadgeItem from './BadgeItem.vue'
import SectionHeader from './SectionHeader.vue'
</script>

<template>
<div class="badge-list-wrapper">
    <SectionHeader label="Badges" />

    <div class="badges">
        <BadgeItem
            iconName="10k-steps"
            title="X Milia"
            explanation="Walk 10'000 steps"
            :progress="95"
        />

        <BadgeItem
            iconName="no-food"
            title="Pestilentia"
            explanation="Starve for 16 hours"
            :progress="2"
        />

        <BadgeItem
            iconName="no-candy"
            title="Cibus Deorum"
            explanation="Consume no sweets"
            :progress="9"
        />

        <BadgeItem
            iconName="no-coffee"
            title="Tardus Mane"
            explanation="Consume no coffee"
            :progress="58"
        />
    </div>
</div>
</template>

<style>
.badge-list-wrapper {
    display: flex;
    flex-direction: column;
}

.badge-list-wrapper .badges {
    display: flex;
    flex-direction: column;
    gap: var(--gap-small);
}
</style>
