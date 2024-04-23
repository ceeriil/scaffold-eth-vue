<template>
  <div :class="[balance ? 'ml-1' : 'ml-1 tooltip tooltip-bottom tooltip-secondary tooltip-open font-bold before:left-auto before:transform-none before:content-[attr(data-tip)] before:right-0']" 
       data-tip="Grab funds from faucet">
    <button class="btn btn-secondary btn-sm px-2 rounded-full">
      <div v-if="!loading">
        <BanknotesIcon class="h-4 w-4" />
      </div>
      <div v-else>
        <span class="loading loading-spinner loading-xs"></span>
      </div>
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue'

import { BanknotesIcon } from "@heroicons/vue/24/outline";

const balance = ref(true);

</script>
