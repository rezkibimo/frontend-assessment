<template>
  <div>
    <h3 class="text-4xl font-extrabold mb-4">Accordion Component</h3>

    <!-- Accordion Title -->
    <div v-for="(item, index) in items" :key="index">
      <button
        class="flex items-center justify-between w-full p-5 font-medium rtl:text-right border border-gray-200 focus:ring-4 focus:ring-blue-200 gap-3"
        :class="{
          'bg-blue-100 border-blue-500 text-blue-600 font-bold':
            activeIndex === index,
        }"
        @click="toggle(index)"
      >
        {{ item.title }}
        <svg
          data-accordion-icon
          class="w-3 h-3 shrink-0"
          :class="{
            'rotate-180': activeIndex === index,
          }"
          aria-hidden="true"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 10 6"
        >
          <path
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M9 5 5 1 1 5"
          />
        </svg>
      </button>

      <!-- Accordion Body -->
      <div :id="index" v-show="activeIndex === index">

        <!-- Accordion Contents uses v-html to inject JSON data and ensure the formatting is correct -->
        <div
          class="p-5 border border-gray-200"
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
