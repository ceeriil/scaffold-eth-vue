<template>
  <div :class="`flex space-x-2 text-sm pointer-events-auto`">
    <input
      id="theme-toggle"
      type="checkbox"
      class="toggle toggle-primary bg-primary hover:bg-primary border-primary"
      @click="ToggleBtn"
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
import { useDark, useToggle, useMounted } from '@vueuse/core';

export default {
  props: {
    className: {
      type: String,
      default: ''
    }
  },
  setup() {
    const isDarkMode = ref(true)
    const toggle = useToggle(isDarkMode)
    
    const ToggleBtn = () => {
      console.log("lol")
      isDarkMode.value = !isDarkMode.value
      const body = document.body;
      body.setAttribute("data-theme", isDarkMode.value ? "scaffoldEthDark" : "scaffoldEth");
    }
    
    const isMounted = useMounted();

    onMounted(() => {
      const body = document.body;
      body.setAttribute("data-theme", isDarkMode ? "scaffoldEthDark" : "scaffoldEth");
      isMounted.value = true;
    });



    return {
      isDarkMode,
      toggle,
      isMounted,
      ToggleBtn
    };
  },
  components: {
    MoonIcon,
    SunIcon
  }
};
</script>

