<script setup lang="ts">
import QRCode from "qrcode";
import { ref, nextTick, onMounted } from "vue";

const slotMessage = ref<HTMLElement | null>(null);
let message: string;

onMounted(() => {
  message = slotMessage?.value?.textContent || "Hello world!";
});

nextTick(() => {
  QRCode.toString(message, {
    color: {
      dark: "#ffffff",
      light: "#3785ff",
    },
    margin: 1,
    errorCorrectionLevel: "quartile",
  }).then((result) => {
    const canvas = document.getElementById("qr-code");
    if (canvas) {
      canvas.innerHTML = result;
    } else {
      console.log("Can't find canvas element");
    }
  });
});
</script>

<template>
  <div class="card">
    <div class="border">
      <div id="qr-code"></div>
    </div>
    <div class="header">
      <slot name="header"> Card Header </slot>
    </div>
    <div class="body" ref="slotMessage">
      <slot>
        {{ message }}
      </slot>
    </div>
  </div>
</template>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  width: 100%;

  background-color: #ffffff;
  border-radius: 0.7rem;
}

.card * {
  padding: 0.8rem;
  text-align: center;
}

.card .header {
  font-weight: bold;
}

.card .border {
  padding: 1rem;
}

.card #qr-code {
  border-radius: 0.5rem;
  background-color: #3785ff;
  padding: 2rem;
  width: 100%;
}
</style>
