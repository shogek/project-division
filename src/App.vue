<script setup lang="ts">
import BadgeList from './components/BadgeList.vue';
import TrackerList from './components/TrackerList.vue';
import ExcerciseList from './components/ExcerciseList.vue';
</script>

<template>
<BadgeList />
<TrackerList />
<ExcerciseList />
</template>

<style>
@import './assets/colors.css';
@import './assets/base.css';

body {
  background: var(--app-background);
  color: var(--font-color);
  padding: var(--gap-small);
  /* TODO: Add font family */
}
</style>
