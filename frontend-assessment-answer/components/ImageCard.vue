<template>
  <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow p-5">
    <NuxtImg
      class="rounded"
      height="300"
      width="400"
      src="https://via.placeholder.com/400x300"
      alt="Card Image"
    />
    <div class="mt-5">
      <p class="mb-4 text-base">
        {{ cardText }}
      </p>
      <div class="flex justify-center">
        <button
          type="button"
          class="bg-white border border-black border-[3px] font-medium rounded-full text-sm font-bold p-3.5 tracking-[0.2em]"
        >
          READ MORE
        </button>
      </div>
    </div>
  </div>
</template>


<script setup>
defineProps({
  cardText: {
    type: String,
    required: true,
  },
});
</script>