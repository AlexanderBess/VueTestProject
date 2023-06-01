<template>
  <div class="navigation__block">
    <img
      class="navigation__logo"
      alt="CellFrame"
      src="~assets/img/app/logo.svg"/>
    <div class="navigation__links">
      <nuxt-link
        v-for="(linkData, key) in navLinks"
        v-bind:key="key"
        class="navigation__link"
        :class="key === activeLink ? 'navigation__link_active' : ''"
        :to="linkData.path"
      >
        <div
          class="navigation__data"
          @click="changeActiveLink(key)">
          <img
              class="navigation__img"
              :alt="linkData.name"
              :src="linkData.imgPath">
          <span class="navigation__name">{{ linkData.name }}</span>
        </div>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavMenu",
  data() {
    return {
      activeLink: 3,
      navLinks: [
        {
          path: '/empty',
          name: 'Wallet',
          imgPath: require('assets/img/app/wallet.svg')
        },
        {
          path: '/empty',
          name: 'DEX',
          imgPath: require('assets/img/app/dex.svg')
        },
        {
          path: '/empty',
          name: 'TX explorer',
          imgPath: require('assets/img/app/explorer.svg')
        },
        {
          path: '/',
          name: 'Certificates',
          imgPath: require('assets/img/app/certificates.svg')
        },
        {
          path: '/empty',
          name: 'Tokens',
          imgPath: require('assets/img/app/tokens.svg')
        },
        {
          path: '/empty',
          name: 'VPN client',
          imgPath: require('assets/img/app/client.svg')
        },
        {
          path: '/empty',
          name: 'VPN service',
          imgPath: require('assets/img/app/service.svg')
        },
        {
          path: '/empty',
          name: 'Console',
          imgPath: require('assets/img/app/console.svg')
        },
        {
          path: '/empty',
          name: 'Logs',
          imgPath: require('assets/img/app/logs.svg')
        },
        {
          path: '/empty',
          name: 'Settings',
          imgPath: require('assets/img/app/settings.svg')
        },
        {
          path: '/empty',
          name: 'dApps',
          imgPath: require('assets/img/app/dapps.svg')
        }
      ]
    }
  },
  methods: {
    changeActiveLink(key) {
      this.activeLink = key;
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
    padding: 14px 0 14px 24px;

    color: $white;
    text-decoration: none;
    &_active {
      background: $black2;
      box-shadow: 1px 1px 0px rgba(107, 102, 126, 0.49), inset 3px 3px 5px rgba(8, 7, 13, 0.25);
      border-radius: 0px 16px 16px 0px;
    }
  }
  &__data {
    display: flex;
    align-items: center;
    gap: 16px;
  }
  &__name {
    font-weight: 400;
    font-size: 13px;
    line-height: 16px;
  }
}

@include _767 {
  .navigation {
    &__block {
      max-width: 150px;
    }
    &__logo {
      padding: 10px 47px 0 8px;
    }
    &__link {
      padding: 14px 0 14px 18px;
    }
    &__data {
      gap: 8px;
    }
  }
}
@include _480 {
  .navigation {
    &__block {
      max-width: 130px;
    }
    &__logo {
      padding: 10px 37px 0 0;
    }
    &__link {
      padding: 10px 0 10px 10px;
    }
    &__data {
      gap: 5px;
    }
  }
}
</style>
