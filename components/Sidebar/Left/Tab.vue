<template>
  <nuxt-link
    to="#"
    class="flex items-center p-3 w-min hover:bg-gray-200 dark:hover:bg-dim-200 dark:text-white text-black rounded-full"
    :class="defaultTransition"
  >
    <div class="w-6 h-6 text-dark">
      <slot name="icon"></slot>
    </div>
    <div class="ml-4 text-xl hidden xl:block" :class="textClass">
      <slot name="name"></slot>
    </div>
  </nuxt-link>
</template>
<script setup>
const { defaultTransition } = useTailwindConfig();
const props = defineProps({
  active: {
    type: Boolean,
    default: false,
  },
});
const textClass = computed(() => (props.active ? "font-semibold" : "normal"));
</script>
