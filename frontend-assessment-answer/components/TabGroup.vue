<template>
  <div>Tablet and Desktop</div>
  <div v-for="(item, index) in items" :key="index">
    {{ item.title }}
    {{ item.content }}
  </div>
</template>

<script setup>
const props = defineProps({
  items: {
    type: Array,
    default: () => [],
  },
});
</script>
