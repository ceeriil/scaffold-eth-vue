<template>
  <ul class="hidden lg:flex lg:flex-nowrap menu menu-horizontal px-1 gap-2">
    <li v-for="link in menuLinks" :key="link.href">
      <NuxtLink
        :to="link.href"
        :class="{
          'bg-secondary shadow-md': isActive,
          'hover:bg-secondary hover:shadow-md focus:!bg-secondary active:!text-neutral py-1.5 px-3 text-sm rounded-full gap-2 grid grid-flow-col': true,
        }"
        passHref
      >
        {{ link.icon }}
        <span>{{ link.label }}</span>
      </NuxtLink>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    menuLinks: {
      type: Array,
      required: true,
    },
  },
  setup() {
    const isActive = false

    return {
      isActive,
    }
  },
}
</script>
