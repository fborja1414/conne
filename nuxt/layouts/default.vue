<template>
  <div class="body-content">
    <Nuxt />
  </div>
</template>

<script>
export default {
  name: "layout",
};
</script>

<style lang="scss">
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
  z-index: 3;
  margin: 0;
  //max-width: 1650px;
  padding: 0 55px;
}
</style>
