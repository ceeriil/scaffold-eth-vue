<template>
  <div class="min-h-0 py-5 px-1 mb-11 lg:mb-0">
    <div>
      <div
        class="fixed flex justify-between items-center w-full z-10 p-4 bottom-0 left-0 pointer-events-none"
      >
        <div class="flex flex-col md:flex-row gap-2 pointer-events-auto">
            <div>
              <div class="btn btn-primary btn-sm font-normal gap-1 cursor-auto">
                <CurrencyDollarIcon class="h-4 w-4" />
                <span>3500.25</span>
              </div>
            </div>
           <EthFaucet />
           <NuxtLink
              to="/blockexplorer"
              class="btn btn-primary btn-sm font-normal gap-1"
            >
              <MagnifyingGlassIcon class="h-4 w-4" />
              <span>Block Explorer </span>
            </NuxtLink>
        </div>
        <SwitchTheme />
      </div>
    </div>
    <div class="w-full">
      <ul class="menu menu-horizontal w-full">
        <div class="flex justify-center items-center gap-2 text-sm w-full">
          <div class="text-center">
            <a
              href="https://github.com/scaffold-eth/se-2"
              target="_blank"
              rel="noreferrer"
              class="link"
            >
              Fork me
            </a>
          </div>
          <span>·</span>
          <div class="flex justify-center items-center gap-2">
            <p class="m-0 text-center">
              Built with <HeartIcon class="inline-block h-4 w-4" /> at
            </p>
            <a
              class="flex justify-center items-center gap-1"
              href="https://buidlguidl.com/"
              target="_blank"
              rel="noreferrer"
            >
              <BuidlGuidlLogo class="w-3 h-5 pb-1" />
              <span class="link">BuidlGuidl</span>
            </a>
          </div>
          <span>·</span>
          <div class="text-center">
            <a
              href="https://t.me/joinchat/KByvmRe5wkR-8F_zz6AjpA"
              target="_blank"
              rel="noreferrer"
              class="link"
            >
              Support
            </a>
          </div>
        </div>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
import { CurrencyDollarIcon, MagnifyingGlassIcon, HeartIcon } from "@heroicons/vue/24/outline";
import BuidlGuidlLogo from "../assets/css/BuidlGuidlLogo.vue";
</script>
