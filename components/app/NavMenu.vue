<template>
  <div class="navigation__block">
    <img
      class="navigation__logo"
      alt="CellFrame"
      src="~assets/img/app/logo.svg"/>
    <div class="navigation__links">
      <nuxt-link
        v-for="(linkData) in navLinks"
        v-bind:key="linkData.id"
        :class="linkData.id === 4 ? 'navigation__link_active' : ''"
        class="navigation__link"
        :to="linkData.path"
      >
        <img
          class="navigation__img"
          :alt="linkData.name"
          :src="linkData.imgPath">
        {{ linkData.name }}
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavMenu",
  data() {
    return {
      navLinks: [
        {
          id: 1,
          path: '/empty',
          name: 'Wallet',
          imgPath: require('assets/img/app/wallet.svg')
        },
        {
          id: 2,
          path: '/empty',
          name: 'DEX',
          imgPath: require('assets/img/app/dex.svg')
        },
        {
          id: 3,
          path: '/empty',
          name: 'TX explorer',
          imgPath: require('assets/img/app/explorer.svg')
        },
        {
          id: 4,
          path: '/',
          name: 'Certificates',
          imgPath: require('assets/img/app/certificates.svg')
        },
        {
          id: 5,
          path: '/empty',
          name: 'Tokens',
          imgPath: require('assets/img/app/tokens.svg')
        },
        {
          id: 6,
          path: '/empty',
          name: 'VPN client',
          imgPath: require('assets/img/app/client.svg')
        },
        {
          id: 7,
          path: '/empty',
          name: 'VPN service',
          imgPath: require('assets/img/app/service.svg')
        },
        {
          id: 8,
          path: '/empty',
          name: 'Console',
          imgPath: require('assets/img/app/console.svg')
        },
        {
          id: 9,
          path: '/empty',
          name: 'Logs',
          imgPath: require('assets/img/app/logs.svg')
        },
        {
          id: 10,
          path: '/empty',
          name: 'Settings',
          imgPath: require('assets/img/app/settings.svg')
        },
        {
          id: 11,
          path: '/empty',
          name: 'dApps',
          imgPath: require('assets/img/app/dapps.svg')
        }
      ]
    }

  }
}
</script>

<style lang="scss" scoped>
.navigation {
  &__block {
    background: $black1;
    border-bottom-right-radius: 30px;
    box-shadow: 0px 3px 15px 9px rgba(8, 7, 13, 0.52)
  }
  &__logo {
    padding: 10px 47px 0 14px;
  }
  &__links {
    display: flex;
    flex-direction: column;
    margin: 0 10px 39px 0;
  }
  &__link {
    display: flex;
    align-items: center;
    padding: 14px 38px 14px 24px;
    gap: 20px;

    font-weight: 400;
    font-size: 13px;
    line-height: 16px;
    color: $white;
    text-decoration: none;
    &_active {
      background: $black2;
      box-shadow: 1px 1px 0px rgba(107, 102, 126, 0.49), inset 3px 3px 5px rgba(8, 7, 13, 0.25);
      border-radius: 0px 16px 16px 0px;
    }
  }
}
</style>
