<template>
  <div>
    <h3 class="text-4xl font-extrabold mb-4">Accordion Component</h3>
    <div v-for="(item, index) in items" :key="index">
      <button
        class="flex items-center justify-between w-full p-5 font-medium rtl:text-right border border-b-0 border-gray-200 focus:ring-4 focus:ring-blue-200 gap-3"
        :class="{
          'bg-blue-100 border-blue-500 text-blue-600 font-bold': activeIndex === index,
        }"
        @click="toggle(index)"
      >
        {{ item.title }}
      </button>

      <div :id="index" v-show="activeIndex === index">
        <div
          class="p-5 border border-b-0 border-gray-200"
          v-html="item.content"
        ></div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  items: {
    type: Array,
    default: () => [],
  },
});

// Accordion item 0 or the first one will always open on load
const activeIndex = ref(0);

function toggle(index) {
  activeIndex.value = activeIndex.value === index ? null : index;
}
</script>
