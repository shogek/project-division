<script setup lang="ts">
const props = defineProps<{
    value: number | string
    width: number
    postfix?: string
}>()

const valueAsString = props.value.toString();
const valueWithPadding = valueAsString.padStart(props.width, '0')
const padding = valueWithPadding.split(valueAsString[0])[0]
</script>

<template>
    <p class="division-text-wrapper">
        <span class="weak">{{ padding }}</span>
        <span class="strong">{{ value }}</span>
        <span v-if="props.postfix" class="strong">{{ props.postfix }}</span>
    </p>
</template>

<style lang="scss">
.division-text-wrapper {
    span {
        font-weight: 300;
    }
    
    .weak {
        color: var(--font-color-weaker);
    }

    .strong {
        color: var(--font-color);
    }
}
</style>
