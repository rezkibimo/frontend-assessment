<template>
  <div>
    <HeroImage />
    <component
      :is="dynamicComponent"
      :items="sectionItems"
      class="px-6 md:px-0"
    />
    <div class="container mx-auto py-8 px-4">
      <div class="max-w-screen-md">
        <h2 class="mb-4 text-4xl tracking-tight font-extrabold">Why banana?</h2>
        <p class="mb-8 font-light sm:text-xl">
          The reason the code snippet given on the repo readme returns 'banana' is that it tries to add the
          strings 'b', 'a' plus 'a', 'a'. Hence, the result becomes 'ba' NaN 'a'
          since 'a' is Not-A-Number (NaN).
        </p>
        <p class="mb-8 font-light sm:text-xl">
          Then all of it is converted to lowercase, making it spell 'banana'.
        </p>
      </div>
    </div>
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

// Bonus point
console.log(("b" + "a" + +"a" + "a").toLowerCase());
</script>
