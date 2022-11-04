<script lang="ts" setup>
export interface commonButton {
  buttonText: string;
  primary?: boolean;
  disabled?: boolean;
  loading?: boolean;
}

const props = withDefaults(defineProps<commonButton>(), {
  primary: false,
  disabled: false,
  loading: false,
});
</script>

<template>
  <button
    class="common-button"
    :class="{ primary: props.primary, disabled: props.disabled }"
  >
    <span v-if="props.loading" class="spinner"></span>
    <div v-else class="common-button-icon">
      <slot></slot>
    </div>
    <span class="common-button-text">
      {{ props.buttonText }}
    </span>
  </button>
</template>

<style lang="scss" scoped>
.common-button {
  outline: none;
  border: none;
  font-size: 1.6rem;
  border-radius: 0.4rem;
  width: max-content;
  height: 4rem;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0 2rem;
  background-color: transparent;
  transition: all 0.3s ease-in-out;
  color: var(--color-text);
  border: 1px solid var(--color-primary-1);

  &:hover {
    cursor: pointer;
    background-color: rgba(255, 255, 255, 0.1);
  }
  .common-button-icon {
    fill: var(--color-text);
    margin-right: 0.4rem;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  &.primary {
    color: #fff;
    background-color: var(--color-primary-1);

    &:hover {
      cursor: pointer;
      background-color: var(--color-primary-2);
    }
    .spinner {
      border-right: 2px solid #fff;
    }
    .common-button-icon {
      fill: #fff;
    }
  }
  &.disabled {
    opacity: 0.7;
    &:hover {
      cursor: default;
      box-shadow: none;
    }
  }
}
.spinner {
  width: 2rem;
  height: 2rem;
  border-radius: 100%;
  border: 2px solid transparent;
  border-right: 2px solid var(--color-text);
  margin-right: 1.2rem;
  animation: spin 0.3s linear infinite;
}
@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
