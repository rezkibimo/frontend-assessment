<template>
  <div class="accordion">
    <div class="accordion-item" v-for="(item, index) in items" :key="index">
      <button class="accordion-header" @click="toggle(index)">
        {{ item.title }}
      </button>
      <div class="accordion-content" v-show="activeIndex === index">
        <slot :name="'content-' + index">{{ item.content }}</slot>
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

<style scoped>
.accordion-item {
  border: 1px solid #ddd;
  margin-bottom: 5px;
}

.accordion-header {
  background: #f1f1f1;
  padding: 10px;
  cursor: pointer;
  border: none;
  width: 100%;
  text-align: left;
}

.accordion-content {
  padding: 10px;
}
</style>
