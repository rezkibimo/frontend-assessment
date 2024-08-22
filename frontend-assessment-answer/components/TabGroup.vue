<template>
  <div class="container m-auto">
    <h3 class="text-4xl font-extrabold mb-4">Tab Group Component</h3>

    <!-- Flex container for the Tab Group and Image -->
    <div class="flex items-start">
      <!-- Image only visible on LG break points and up -->
      <NuxtImg
        class="lg:mr-4 lg:basis-6/12 lg:block hidden"
        height="300"
        width="400"
        src="https://via.placeholder.com/400x300"
        alt="Card Image"
        lazy
      />
      <div class="lg:basis-6/12">
        <!-- Tab Name -->
        <div class="mb-4 border-b border-gray-200">
          <ul
            class="flex flex-wrap -mb-px text-sm font-medium text-center"
            role="tablist"
          >
            <li v-for="(tab, index) in items" :key="tab.index">
              <button
                class="inline-block p-4 border-b-2 rounded-t-lg"
                :class="{
                  'border-blue-500 text-blue-600': currentTab === index,
                }"
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
            class="p-4 rounded-lg bg-gray-50"
            :id="tab.index"
            role="tabpanel"
            :aria-labelledby="`tab-${index}`"
            v-show="currentTab === index"
            v-html="tab.content"
          ></div>
        </div>
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

// Tab item 0 or the first one will always open on load
const currentTab = ref(0);
</script>
