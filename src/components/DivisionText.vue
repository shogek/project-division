<script setup lang="ts">
import { computed, ref, toRefs, watch } from 'vue';

const props = defineProps<{
    value: number | string
    width: number
    postfix?: string
}>()

const valueRef = toRefs(props).value
const widthRef = toRefs(props).width

const padding$ = computed(() => {
    const valueAsString = valueRef.value.toString();
    const valueWithPadding = valueAsString.padStart(widthRef.value, '0')
    return valueWithPadding.substring(0, props.width - valueAsString.length)
})
</script>

<template>
    <p class="division-text-wrapper">
        <span class="weak">{{ padding$ }}</span>
        <span class="strong">{{ valueRef }}</span>
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
