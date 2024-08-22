<template>
  <div>
    <HeroImage />
    <component :is="dynamicComponent" :items="sectionItems" class="px-6 md:px-0" />
  </div>
</template>

<script setup>
import { Accordion, TabGroup } from "#components";
import sectionItems from "~/data/data.json";


// Dynamic component by default is Tab Group
const dynamicComponent = shallowRef(TabGroup);

// Check if the screen width is les than 640px if yes the it become Accordion else it become Tab Group
function updateComponent() {
  dynamicComponent.value = window.innerWidth < 640 ? Accordion : TabGroup;
}

// add event listener on mount to check for window size 
onMounted(() => {
  updateComponent();
  window.addEventListener("resize", updateComponent);
});

watch(() => window.innerWidth, updateComponent);
</script>
