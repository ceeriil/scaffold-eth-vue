<template>
  <div
    :class="[
      'flex',
      'border-2',
      'border-base-300',
      'bg-base-200',
      'rounded-full',
      'text-accent',
      modifier,
    ]"
  >
    <slot name="prefix"></slot>
    <input
      class="input input-ghost focus-within:border-transparent focus:outline-none focus:bg-transparent focus:text-gray-400 h-[2.2rem] min-h-[2.2rem] px-4 border w-full font-medium placeholder:text-accent/50 text-gray-400"
      :placeholder="placeholder"
      :name="name"
      :value="valueToString"
      @input="handleChange"
      :disabled="disabled"
      autocomplete="off"
    />
    <slot name="suffix"></slot>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

const props = defineProps<{
  name: string;
  value: string | number | object;
  placeholder: string;
  error?: boolean;
  disabled?: boolean;
  prefix?: string | object;
  suffix?: string | object;
  onChange?: (value: string) => void;
}>();

const modifier = props.error
  ? "border-error"
  : props.disabled
  ? "border-disabled bg-base-300"
  : "";

const valueToString = () => {
  return props.value ? props.value.toString() : "";
};

const handleChange = (event: InputEvent) => {
  if (props.onChange) {
    props.onChange((event.target as HTMLInputElement).value);
  }
};
</script>

<style scoped>
/* Add your scoped styles here */
</style>
