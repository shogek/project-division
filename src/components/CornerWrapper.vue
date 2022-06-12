<script setup lang="ts">

</script>

<template>
<div class="corner-wrapper">
    <slot />
</div>
</template>

<style>
.corner-wrapper {
    padding: calc(var(--app-corner-height) / 2);

    background:
        linear-gradient(to right, var(--app-corner-color), var(--app-corner-color)),
        linear-gradient(to right, var(--app-corner-color), var(--app-corner-color)),
        linear-gradient(to right, var(--app-corner-color), var(--app-corner-color)),
        linear-gradient(to right, var(--app-corner-color), var(--app-corner-color));

    background-repeat:
        no-repeat,
        no-repeat,
        no-repeat,
        no-repeat;

    background-position:
        top left,
        top right,
        bottom right,
        bottom left;

    background-size:
        var(--app-corner-height) var(--app-corner-height),
        var(--app-corner-height) var(--app-corner-height),
        var(--app-corner-height) var(--app-corner-height),
        var(--app-corner-height) var(--app-corner-height);
}
</style>