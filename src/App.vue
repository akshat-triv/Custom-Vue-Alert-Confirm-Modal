<script lang="ts" setup>
import CommonButton from "./components/CommonButton.vue";
import AlertConfirmModal from "./components/AlertConfirmModal.vue";

import { ref } from "vue";

const alertConfirm = ref<InstanceType<typeof AlertConfirmModal> | null>(null);

async function openAlertConfirm(alertModal = false) {
  const alertMessage =
    "Hi!, You created a custom async alert modal. This was amazing.";

  const confirmMessage = "It was quite interesting and elegant right?";

  const userInput = await alertConfirm.value?.openModal(
    alertModal ? alertMessage : confirmMessage,
    alertModal
  );

  console.log("This was the user input", userInput);
}
</script>

<template>
  <div class="buttons-wrapper">
    <CommonButton
      button-text="Open Alert"
      :primary="true"
      @click="openAlertConfirm(true)"
    />
    <CommonButton
      button-text="Open Confirm"
      :primary="true"
      @click="openAlertConfirm(false)"
    />
  </div>
  <div class="alert-modal">
    <AlertConfirmModal ref="alertConfirm" />
  </div>
</template>

<style lang="scss">
.buttons-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;

  width: 720px;
  margin: 0 auto;
}
.alert-modal {
  width: 100%;
  flex: 1;
  position: relative;

  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
