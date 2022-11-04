<script lang="ts" setup>
const props = defineProps({
  title: {
    type: String,
    default: "Cancle",
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
      d="M10 9.293l3.646-3.647.708.708L10.707 10l3.647 3.646-.707.708L10 10.707l-3.646 3.647-.708-.707L9.293 10 5.646 6.354l.708-.708L10 9.293z"
      clip-rule="evenodd"
    />
  </svg>
</template>
