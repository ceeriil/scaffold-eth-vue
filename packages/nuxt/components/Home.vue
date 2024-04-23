<template>
  <div class="flex items-center flex-col flex-grow pt-10">
    <div class="px-5">
      <h1 class="text-center mb-8">
        <span class="block text-2xl mb-2">Welcome to</span>
        <span class="block text-4xl font-bold">Scaffold-ETH 2 Vue</span>
      </h1>
      <p class="text-center text-lg">
        Get started by editing
        <code
          class="italic bg-base-300 text-base font-bold max-w-full break-words break-all inline-block"
        >
          packages/nuxtjs/pages/index.tsx
        </code>
      </p>
      <p class="text-center text-lg">
        Edit your smart contract
        <code
          class="italic bg-base-300 text-base font-bold max-w-full break-words break-all inline-block"
        >
          YourContract.sol
        </code>
        in
        <code
          class="italic bg-base-300 text-base font-bold max-w-full break-words break-all inline-block"
        >
          packages/hardhat/contracts
        </code>
      </p>
    </div>

    <div class="flex-grow bg-base-300 w-full mt-16 px-8 py-12">
      <div class="flex justify-center items-center gap-12 flex-col sm:flex-row">
        <div
          class="flex flex-col bg-base-100 px-10 py-10 text-center items-center max-w-xs rounded-3xl"
        >
          <BugAntIcon class="h-8 w-8 fill-secondary" />
          <p>
            Tinker with your smart contract using the
            <NuxtLink to="/debug" passHref class="link">
              Debug Contract
            </NuxtLink>
            tab.
          </p>
        </div>
        <div
          class="flex flex-col bg-base-100 px-10 py-10 text-center items-center max-w-xs rounded-3xl"
        >
          <MagnifyingGlassIcon class="h-8 w-8 fill-secondary" />
          <p>
            Explore your local transactions with the
            <NuxtLink to="/blockexplorer" passHref class="link">
              Block Explorer
            </NuxtLink>
            tab.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { BugAntIcon, MagnifyingGlassIcon } from "@heroicons/vue/24/outline";
</script>
