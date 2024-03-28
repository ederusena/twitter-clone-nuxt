<template>
  <NuxtLink to="#" class="flex items-center text-black p-3 w-min rounded-full hover:bg-slate-300 dark:hover:bg-dim-200 dark:text-white" :class="defaultTransition">
    <div class="size-6 text-dark">
      <slot name="icon" />

    </div>
    <div class="hidden xl:block ml-4 text-xl" :class="[textClasses]">
      <slot name="name" />

    </div>
  </NuxtLink>
</template>

<script setup lang="ts">
const { defaultTransition } = useTailwindConfig()

interface Props {
  active: Boolean
}

const props = defineProps<Props>()

const textClasses = computed(() => {
  return {
    'font-semibold text-white': props.active,
    'font-normal': !props.active,
  }
})
</script>