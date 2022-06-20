<script setup lang="ts">
import { ref, toRefs } from 'vue';
import DivisionText from './DivisionText.vue'

const props = defineProps<{
    value: number
    width: number
}>()

const emits = defineEmits<{
    (eventName: 'changed', value: number): void
}>()

function onClick() {
    isFocused$.value = true
    inputRef$.value!.focus()
    inputRef$.value!.click()
}

function onChange() {
    const newValue = +inputRef$.value?.value!
    inputValue$.value = newValue
    emits('changed', newValue)
}

function onBlur() {
    isFocused$.value = false
}

const valueRef = toRefs(props).value

const inputRef$ = ref<HTMLInputElement | null>(null)
const isFocused$ = ref(false)
const inputValue$ = ref(valueRef.value)
</script>

<template>
    <div class="division-input-wrapper">
        <input ref="inputRef$" @input="onChange" @blur="onBlur()" class="hidden-input" type="number" />
        <div @click="onClick()" class="input" :class="{ focused: isFocused$ }">
            <DivisionText :value="inputValue$" :width="width" />
        </div>
    </div>
</template>

<style lang="scss">
.division-input-wrapper {
    .hidden-input {
        position: absolute;
        right: -9999px;
        left: -9999px;
    }

    .input {
        border-bottom: 1px dashed var(--division-color);

        &.focused {
            border-bottom-style: solid;
        }
    }
}
</style>