<template>
  <div class="empty__content">
    <img src="~/assets/img/ui/empty.jpg" alt="empty">
  </div>
</template>

<script>
export default {
  name: "empty"
}
</script>

<style lang="scss" scoped>
  .empty__content {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  @include _991() {
    .empty__content img {
      width: inherit;
    }
  }
</style>
