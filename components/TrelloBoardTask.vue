<script setup lang="ts">
import type {Task} from "~/types";

defineProps<{
  task: Task
}>()
</script>

<template>
  <div :title="task.createdAt.toLocaleString()"
       class="task bg-white p-2 mb-2 rounded max-w-[520px] flex">
    <Icon class="drag-handle cursor-move min-w-[15px]" name="material-symbols:table-rows-narrow-outline"/>

    {{ task.title }}
  </div>
</template>

<style scoped>
.sortable-drag .task {
  transform: rotate(5deg);
}

.sortable-ghost .task {
  position: relative;
}

.sortable-ghost .task:after {
  content: "";
  @apply absolute top-0 bottom-0 left-0 right-0 bg-slate-300 rounded;
}
</style>
