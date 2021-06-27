<template>
  <div class="body-content">
    <Nuxt />
    <Matter />
  </div>
</template>

<script>
import Matter from "@/components/Matter.vue";

export default {
  name: "layout",
  components: {
    Matter
  }
};
</script>

<style>
html {
  font-family: "Neue Haas Grotesk", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.body-content {
  position: relative;
  overflow: scroll;
}
</style>
