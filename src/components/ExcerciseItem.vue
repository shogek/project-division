<script setup lang="ts">
import { ref } from 'vue';
import CustomIcon from './CustomIcon.vue'
import DivisionText from './DivisionText.vue'
import DivisionInput from './DivisionInput.vue'

const props = defineProps<{
    /** TODO: Explain me */
    iconName: string
    /** TODO: Explain me */
    name: string
    /** TODO: Explain me */
    sets: number[]
}>()

function toggleSetVisibility() {
    isExpanded$.value = !isExpanded$.value
}

function removeSet(index: number) {
    setList$.value = setList$.value.filter((_, i) => i !== index);
}

function onNewSetRepsChanged(newValue: number) {
    newSetReps$.value = newValue
}

function addSet() {
    setList$.value = [...setList$.value, newSetReps$.value]
    newSetReps$.value = 0;
}

function cancelChanges() {
    setList$.value = props.sets;
}

function confirmChanges() {
    // TODO: Implement me
}

// const isExpanded$ = ref(false);
const isExpanded$ = ref(true);
const setList$ = ref(props.sets);
const newSetReps$ = ref(0);
const totalReps = props.sets.reduce((prev, curr) => prev + curr, 0)
const maxReps = props.sets.reduce((prev, curr) => curr > prev ? curr : prev, 0)
</script>

<template>
    <div class="excercise-item-wrapper corner-border-2 corner-border-3">
        <div class="border">
            <div @click="toggleSetVisibility()" class="title-row corner-1 corner-4">
                <div class="icon">
                    <CustomIcon :iconName="iconName" />
                </div>
                <h4 class="title corner-1 corner-4">{{ name }}</h4>
            </div>
            <div class="stats-row corner-2 corner-3">
                <div class="vertical corner-4">
                    <p class="heading">Sets</p>
                    <DivisionText :value="props.sets.length" :width="2" />
                </div>

                <div class="vertical corner-1 corner-4">
                    <p class="heading">Total</p>
                    <DivisionText :value="totalReps" :width="5" />
                </div>

                <div class="vertical corner-1 corner-4">
                    <p class="heading">Max</p>
                    <DivisionText :value="maxReps" :width="5" />
                </div>
            </div>
        </div>

        <div v-if="isExpanded$" class="sets-row">
            <div v-for="set, i in setList$" class="set corner-border-3">
                <div class="index corner-1 corner-4">
                    <DivisionText :value="i + 1" :width="2" />
                </div>

                <div class="reps corner-1 corner-4">
                    <p>Reps performed</p>
                    <DivisionInput :value="set" :width="5" />
                </div>

                <div class="actions corner-1 corner-4">
                    <div @click="removeSet(i)" class="remove"></div>
                </div>
            </div>

            <div class="set corner-border-3">
                <div class="index corner-1 corner-4">
                    <DivisionText value="N" :width="1" />
                </div>

                <div class="reps corner-1 corner-4">
                    <p>Reps performed</p>
                    <DivisionInput @changed="onNewSetRepsChanged" :value="newSetReps$" :width="5" />
                </div>

                <div class="actions corner-1 corner-4">
                    <div @click="addSet()" class="add"></div>
                </div>
            </div>

            <div class="action-buttons">
                <div @click="cancelChanges()" class="button">
                    <span class="letter">B</span>
                    <div class="separator corner-2 corner-3"></div>
                    <span>Cancel</span>
                </div>

                <div class="button">
                    <span class="letter">X</span>
                    <div class="separator corner-2 corner-3"></div>
                    <span>Confirm</span>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">

.excercise-item-wrapper {
    display: flex;
    flex-direction: column;

    .border {
        border: var(--app-border);
    }

    .title-row {
        display: flex;
        flex-direction: row;
        height: var(--excercise-card-height);
        border: var(--app-border);
        border-right: none;
        border-top: none;
        border-left: none;

        .icon {
            display: grid;
            place-items: center;
            padding: var(--gap-medium);
            border: var(--app-border);
            border-left: none;
            border-top: none;
            border-bottom: none;

            svg {
                height: var(--excercise-icon-height);
            }
        }

        .title {
            display: flex;
            align-items: center;
            flex-grow: 1;
            font-size: 1.4em;
            padding: var(--gap-medium);
        }
    }

    .stats-row {
        display: flex;
        flex-direction: row;

        .vertical {
            display: flex;
            flex-direction: column;
            flex-grow: 1;
            justify-content: center;
            align-items: center;
            gap: var(--gap-small);
            padding: var(--gap-small);
            border: var(--app-border);
            border-left: none;
            border-top: none;
            border-bottom: none;

            &:last-child {
                border-right: none;
            }
        }
    }

    .sets-row {
        .set {
            display: flex;
            flex-direction: row;
            height: var(--excercise-set-height);

            .index {
                display: grid;
                place-items: center;
                width: var(--excercise-set-height);
                padding: var(--gap-small);
                border-left: var(--app-border);
                border-bottom: var(--app-border);
            }

            .reps {
                display: flex;
                flex-direction: row;
                align-items: center;
                gap: var(--gap-medium);
                flex-grow: 1;
                padding: var(--gap-small);
                border-left: var(--app-border);
                border-bottom: var(--app-border);

                p {
                    color: var(--font-color-weaker);
                }

                input {
                    width: 3ch;
                }
            }

            .actions {
                width: var(--excercise-set-height);
                border-left: var(--app-border);
                border-right: var(--app-border);
                border-bottom: var(--app-border);

                .remove {
                    width: 100%;
                    height: 100%;

                    &::before {
                        display: block;
                        position: absolute;
                        content: "";
                        width: 50%;
                        height: 50%;
                        transform: rotate(225deg);
                        border: solid 1px var(--font-color);
                        border-top: none;
                        border-bottom: none;
                        border-right: none;
                        top: 6%;
                        left: 9%;
                    }

                    &::after {
                        display: block;
                        position: absolute;
                        content: "";
                        width: 50%;
                        height: 50%;
                        transform: rotate(135deg);
                        border: solid 1px var(--font-color);
                        border-left: none;
                        border-top: none;
                        border-bottom: none;
                        right: 5%;
                        bottom: 44%;
                    }
                }

                .add {
                    width: 100%;
                    height: 100%;

                    &::before {
                        display: block;
                        position: absolute;
                        content: "";
                        width: 50%;
                        height: 50%;
                        transform: rotate(225deg);
                        border: solid 1px var(--font-color);
                        border-top: none;
                        border-bottom: none;
                        border-right: none;
                        top: 14%;
                        left: 16%;
                    }

                    &::after {
                        display: block;
                        position: absolute;
                        content: "";
                        width: 50%;
                        height: 18%;
                        transform: rotate(135deg);
                        border: solid 1px var(--font-color);
                        border-left: none;
                        border-top: none;
                        border-bottom: none;
                        right: 25%;
                        bottom: 42%;
                    }
                }
            }
        }

        .action-buttons {
            display: flex;
            flex-direction: row;
            justify-content: space-around;
            margin: var(--gap-medium) 0;

            .button {
                display: flex;
                padding: 0 var(--gap-small);
                gap: var(--gap-small);
                background-color: var(--button-background-color);

                .letter {
                    color: var(--division-color);
                }

                .separator {
                    border: var(--app-border);
                    border-left: none;
                    border-top: none;
                    border-bottom: none;
                }
                // .letter::after {
                //     position: relative;
                //     content: '';
                //     // border: solid 1px black;
                //     height: 100%;
                // }
            }
        }
    }
}
</style>
