<script setup lang="ts">
import QRCodeComponent from "./components/QRCodeComponent.vue";
</script>

<template>
  <header>QR-Code Component Frontend Mentor Challenge</header>
  <main>
    <QRCodeComponent></QRCodeComponent>
  </main>

  <footer>
    <div class="attribution">
      Challenge by
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">
        Frontend Mentor
      </a>
      Coded by <a href="https://github.com/parapente">Theofilos Intzoglou</a>.
    </div>
  </footer>
</template>

<style scoped>
header {
  line-height: 1.5;
  text-align: center;
}

main {
  flex-grow: 1;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

.attribution {
  font-size: 11px;
  text-align: center;
}

.attribution a {
  color: hsl(228, 45%, 44%);
}
</style>
