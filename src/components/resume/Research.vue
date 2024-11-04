<script lang="ts" setup>
import type { Project } from '~/types/base'

const props = defineProps<{ research: Project }>()
const { research } = toRefs(props)
</script>

<template>
  <div v-if="research" class="resume-projects">
    <base-title :icon="research.icon" :title="research.title" />
    <ProjectItem v-for="set in research.sets" :key="set.name" :set="set" />
  </div>
</template>

<style lang="scss">
.project-name {
  margin-left: 4px;
}
</style>
