<template>
  <div>
    <HeroImage />
    <!-- Cards Grid -->
    <div class="flex flex-wrap gap-10 justify-center px-6 md:px-0">
      <ImageCard
        v-for="(card, index) in cards"
        :key="index"
        :cardText="card.text"
      />
    </div>
  </div>
</template>

<script setup>
const cards = [
  {
    text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
  },
  {
    text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
  },
  {
    text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco.",
  },
];
</script>
