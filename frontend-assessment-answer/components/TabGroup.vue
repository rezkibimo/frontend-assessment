<template>
  <div class="container m-auto">
    <h1 class="h1">Tablet and Desktop</h1>

    <!-- Tab Name -->
    <div class="mb-4 border-b border-gray-200 dark:border-gray-700">
      <ul class="flex flex-wrap -mb-px text-sm font-medium text-center" role="tablist">
        <li v-for="(tab, index) in items" :key="tab.index">
          <button
            class="inline-block p-4 border-b-2 rounded-t-lg"
            :class="{ 'border-blue-500 text-blue-600': currentTab === index }"
            @click="currentTab = index"
            role="tab"
            :aria-controls="tab.index"
            :aria-selected="currentTab === index"
          >
            {{ tab.title }}
          </button>
        </li>
      </ul>
    </div>

    <!-- Tab Contents -->
    <div>
      <div
        v-for="(tab, index) in items"
        :key="tab.index"
        class="p-4 rounded-lg bg-gray-50 dark:bg-gray-800"
        :id="tab.index"
        role="tabpanel"
        :aria-labelledby="`tab-${index}`"
        v-show="currentTab === index"
      >
        {{ tab.content }}
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

const currentTab = ref(0);

</script>
