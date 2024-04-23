<template>
     <div :class="`flex space-x-2 text-sm ${className}`">
    <input
      id="theme-toggle"
      type="checkbox"
      class="toggle toggle-primary bg-primary hover:bg-primary border-primary"
      @change="toggle"
      :checked="isDarkMode"
    />
    <label v-if="isMounted" for="theme-toggle" :class="`swap swap-rotate ${!isDarkMode ? 'swap-active' : ''}`">
      <SunIcon class="swap-on h-5 w-5" />
      <MoonIcon class="swap-off h-5 w-5" />
    </label>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';
import { MoonIcon, SunIcon } from "@heroicons/vue/24/outline";

export default {
  props: {
    className: {
      type: String,
      default: ''
    }
  },
  setup() {
    const { isDarkMode, toggle } = false;
    const isMounted = ref(false);

    onMounted(() => {
      const body = document.body;
      body.setAttribute("data-theme", isDarkMode ? "scaffoldEthDark" : "scaffoldEth");
      isMounted.value = true;
    });

    return {
      isDarkMode,
      toggle,
      isMounted
    };
  },
  components: {
    MoonIcon,
    SunIcon
  }
};
</script>

