<script setup lang="ts">
import Icon10kSteps from './icons/Icon10kSteps.vue'
import IconCandy from './icons/IconCandy.vue'
import IconCardio from './icons/IconCardio.vue'
import IconChocos from './icons/IconChocos.vue'
import IconCoffee from './icons/IconCoffee.vue'
import IconNoFood from './icons/IconNoFood.vue'
import IconNoCandy from './icons/IconNoCandy.vue'
import IconNoCoffee from './icons/IconNoCoffee.vue'
import IconPleasure from './icons/IconPleasure.vue'
import IconPullUp from './icons/IconPullUp.vue'
import IconPushUp from './icons/IconPushUp.vue'
import IconRandomSport from './icons/IconRandomSport.vue'

defineProps<{
    /** TODO: Explain me */
    // TODO: Use enum for all available icons?
    iconName: string
}>()
</script>

<template>
    <Icon10kSteps v-if="iconName === '10k-steps'" />
    <IconCandy v-if="iconName === 'candy'" />
    <IconCardio v-if="iconName === 'cardio'" />
    <IconChocos v-if="iconName === 'chocos'" />
    <IconCoffee v-if="iconName === 'coffee'" />
    <IconNoFood v-if="iconName === 'no-food'" />
    <IconNoCandy v-if="iconName === 'no-candy'" />
    <IconNoCoffee v-if="iconName === 'no-coffee'" />
    <IconPleasure v-if="iconName === 'pleasure'" />
    <IconPullUp v-if="iconName === 'pull-up'" />
    <IconPushUp v-if="iconName === 'push-up'" />
    <IconRandomSport v-if="iconName === 'random-sport'" />
</template>
