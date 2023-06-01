<template>
  <div class="primary">
    <div class="primary__body">
      <NavMenu/>
      <nuxt class="primary__content"/>
    </div>
    <div class="primary__footer footer">
      <Footer/>
    </div>
  </div>
</template>

<script>
export default {
  name: "default"
}
</script>

<style lang="scss" scoped>
  .primary {
    display: grid;
    grid-template-rows: 1fr auto;
    height: 100vh;
    overflow-y: auto;
    background: $black2;
    font-family: 'Quicksand-Regular', sans-serif;
    font-style: normal;
    color: $white;
    &__body {
      display: flex;
      justify-content: flex-start;
      gap: 3px;
    }
    &__content {
      display: flex;
      flex-direction: column;
      width: 100%;
    }
  }
</style>
