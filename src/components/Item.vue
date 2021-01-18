<template>
  <div class="grid grid-cols-12 overflow-hidden col-gap-6 mb-5">
    <img class="block col-span-3 w-full h-20 rounded bg-gray-600" src alt />
    <div class="col-span-5 ml-3">
      <div class="flex">
        <h6 class="text-sm font-semibold text-gray-800 flex-grow">
          {{ item.title }}
        </h6>
      </div>
      <p class="text-xs truncate text-gray-600">{{ item.description }}</p>
      <span class="text-sm text-gray-800">{{ item.price }} USD</span>
    </div>
  </div>
</template>
<script>
export default {
  name: "Item",
  props: {
    item: Object,
  },
};
</script>