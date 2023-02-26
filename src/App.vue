<script setup lang="ts">
import Calculator from "./components/Calculator.vue";
import FooterSignature from "./components/FooterSignature.vue";
</script>

<template>
  <main>
    <calculator />
  </main>
  <footer>
    <a href="https://github.com/UendelC" target="__blank">
      <p>
        Uendel Couto
      </p>
    </a>
  </footer>
</template>

<style scoped>

main {
  height: 100vh;
  width: 100vw;
  background: linear-gradient(#807ece, #8e7ece);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

footer {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100vw;
  height: 20px;
  background-color: linear-gradient(#807ece, #8e7ece);
}

footer p {
  text-align: center;
  font-size: 12px;
  color: black;
  opacity: 100%;
  z-index: 0;
}

</style>
