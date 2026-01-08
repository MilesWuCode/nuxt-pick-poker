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
  <div>
    <img
      v-if="!selected"
      src="/images/cat.jpg"
      class="border border-blue-500 object-fill w-70 h-100"
    />
    <div
      v-else
      class="bg-white text-black p-2 rounded text-center w-full h-full border border-green-400"
    >
      {{ data.name }} - {{ data.id }}
    </div>
  </div>
</template>
