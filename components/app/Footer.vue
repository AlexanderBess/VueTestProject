<template>
  <div class="footer__block">
    <div
      v-for="(data) in footerData"
      class="footer__element">
      {{ data.name }}
      <div
        class="element__status"
        :class="`element__status_${data.status}`"/>
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      footerData: [
        {
          name: 'Cellnet',
          status: 'active'
        },
        {
          name: 'Mainnet',
          status: 'active'
        },
        {
          name: 'Somenet',
          status: 'active'
        },
        {
          name: 'Testnet',
          status: 'active'
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.footer {
  &__block {
    display: flex;
    align-items: center;
    justify-content: space-around;
    margin-top: 5px;
    background: #2E3138;
    box-shadow: 5px -5px 10px rgba(8, 7, 13, 0.42), inset 1px 1px 0px #524D64;
  }
  &__element {
    height: 42px;
    display: flex;
    align-items: center;
    gap: 8px;

    font-weight: 500;
    font-size: 12px;
    line-height: 15px;
  }
}
.element {
  &__status {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    &_active {
      background: radial-gradient(50% 50% at 50% 50%, #A9E81C 0%, #8ECC00 100%);
    }
  }
}
</style>
