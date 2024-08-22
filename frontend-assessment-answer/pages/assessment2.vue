<template>
  <div>
    <HeroImage />
    <component :is="dynamicComponent" :items="sectionItems" />
  </div>
</template>

<script setup>
import { Accordion, TabGroup } from "#components";
import sectionItems from "~/data/data.json";

const dynamicComponent = shallowRef(Accordion);

function updateComponent() {
  dynamicComponent.value = window.innerWidth < 640 ? Accordion : TabGroup;
}

onMounted(() => {
  updateComponent();
  window.addEventListener("resize", updateComponent);
});

watch(() => window.innerWidth, updateComponent);
</script>
