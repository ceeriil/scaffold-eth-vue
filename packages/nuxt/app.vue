<template>
  <NuxtLayout name="default">
    <button>hello</button>
    <NuxtPage />
  </NuxtLayout>
</template>

<script setup lang="ts">
import { createWeb3Modal, defaultWagmiConfig } from "@web3modal/wagmi/vue";

import { mainnet, arbitrum, sepolia } from "viem/chains";
import { reconnect } from "@wagmi/core";

// 1. Define constants
const projectId = "309449c6694a995ac58b90eb5b3206af";

const metadata = {
  name: "Web3Modal",
  description: "Web3Modal Example",
  url: "https://web3modal.com",
  icons: ["https://avatars.githubusercontent.com/u/37784886"],
};

const chains = [mainnet, arbitrum];
const config = defaultWagmiConfig({
  chains,
  projectId,
  metadata,
  // Optional - Override createConfig parameters
});

reconnect(config);
createWeb3Modal({
  wagmiConfig: config,
  projectId,
  enableAnalytics: true,
  enableOnramp: true,
});
</script>
