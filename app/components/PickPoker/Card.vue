<script setup lang="ts">
defineProps<{
  data: {
    id: number;
    name: string;
  };
  selected: boolean;
}>();
</script>

<template>
  <img v-if="!selected" src="/images/cat.jpg" class="w-70 h-100 rounded-xl" />
  <div
    v-else
    class="bg-blue-100 text-black p-2 rounded-xl text-center w-full h-full"
  >
    {{ data.name }} - {{ data.id }}
  </div>
</template>
