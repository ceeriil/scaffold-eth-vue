<template>
  <div
    class="sticky lg:static top-0 navbar bg-base-100 min-h-0 flex-shrink-0 justify-between z-20 shadow-md shadow-secondary px-0 sm:px-2"
  >
    <div class="navbar-start w-auto lg:w-1/2">
      <div class="lg:hidden dropdown" ref="burgerMenuRef">
        <label
          tabindex="0"
          class="ml-1 btn btn-ghost"
          :class="{
            'hover:bg-secondary': isDrawerOpen,
            'hover:bg-transparent': !isDrawerOpen,
          }"
          @click="toggleDrawer"
        >
          <Bars3Icon class="h-1/2" />
        </label>
        <div
          v-if="isDrawerOpen"
          tabindex="0"
          class="menu menu-compact dropdown-content mt-3 p-2 shadow bg-base-100 rounded-box w-52"
          @click="closeDrawer"
        >
          <HeaderMenuLinks :menuLinks="menuLinks" />
        </div>
      </div>
      <NuxtLink
        to="/"
        passHref
        class="hidden lg:flex items-center gap-2 ml-4 mr-6 shrink-0"
      >
        <div class="flex relative w-10 h-10">
          <img alt="SE2 logo" class="cursor-pointer" fill src="/logo.svg" />
        </div>
        <div class="flex flex-col">
          <span class="font-bold leading-tight">Scaffold-ETH Vue</span>
          <span class="text-xs">Ethereum dev stack</span>
        </div>
      </NuxtLink>
      <div
        class="hidden lg:flex lg:flex-nowrap menu menu-horizontal px-1 gap-2"
      >
        <HeaderMenuLinks :menuLinks="menuLinks" />
      </div>
    </div>
    <div class="navbar-end flex-grow mr-4">
      <CustomConnectButton />
      <EthFaucetButton />
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const isDrawerOpen = ref(false);
const burgerMenuRef = ref(null);

const toggleDrawer = () => {
  isDrawerOpen.value = !isDrawerOpen.value;
};

const closeDrawer = () => {
  isDrawerOpen.value = false;
};

const handleClickOutside = (event) => {
  if (burgerMenuRef.value && !burgerMenuRef.value.contains(event.target)) {
    closeDrawer();
  }
};

onMounted(() => {
  document.addEventListener("click", handleClickOutside);
});

onUnmounted(() => {
  document.removeEventListener("click", handleClickOutside);
});

const menuLinks = [
  {
    label: "Home",
    href: "/",
  },
  {
    label: "Debug Contracts",
    href: "/debug",
  },
];
</script>
