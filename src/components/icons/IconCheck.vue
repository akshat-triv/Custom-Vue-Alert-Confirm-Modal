<script lang="ts" setup>
const props = defineProps({
  title: {
    type: String,
    default: "Check",
  },
});
</script>

<template>
  <svg
    xmlns="http://www.w3.org/2000/svg"
    width="20"
    height="20"
    viewBox="0 0 20 20"
    fill="currentColor"
  >
    <title>{{ props.title }}</title>
    <path
      fill-rule="evenodd"
      d="M15.927 5.76l-5.354 8.761A1 1 0 0 1 9.72 15H8.245a1 1 0 0 1-.79-.386l-3.35-4.307.79-.614L8.245 14H9.72l5.353-8.76.854.52z"
      clip-rule="evenodd"
    />
  </svg>
</template>
