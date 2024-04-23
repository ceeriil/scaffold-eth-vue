<template>
   <button className="btn btn-primary btn-sm" type="button" @click="modal.open()">
                    Connect Wallet
                  </button>
</template>

<script setup>
  import { useWeb3Modal } from '@web3modal/ethers5/vue';

  const modal = useWeb3Modal()
</script>
