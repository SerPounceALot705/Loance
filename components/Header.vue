<template>
  <div>
    <section class="header">
      <a href="/" class="header-logo-container">
        <img
          class="header-logo"
          alt="logo"
          :src="require('~/assets/images/logo.png')"
        />
        <img
          class="header-name"
          alt="logo-name"
          :src="require('~/assets/images/loance.png')"
        />
        <p class="keymat-logo">by Keymat</p>
      </a>
      <div class="header-menu-item-container">
        <ul class="header-menu">
          <li>
            <a href="" class="header-link">
              <img
                class="header-menu-img_accounting"
                alt="accounting"
                :src="require('~/assets/images/001-accounting.png')"
              />
              <span class="header-menu-text">Займ</span>
            </a>
            <div
              :class="{
                'header-menu-underline_actived': selectLine == 'default',
              }"
            ></div>
          </li>
          <li>
            <a href="" class="header-link">
              <img
                class="header-menu-img"
                alt="investments"
                :src="require('~/assets/images/001-return.png')"
              />
              <span class="header-menu-text">Инвестиции</span>
            </a>
          </li>
        </ul>
        <div class="header-menu-underline"></div>
      </div>
      <div class="header-menu-item-container">
        <ul class="header-transaction">
          <li>
            <a href="" class="header-link header-link-transaction">
              <img
                class="header-menu-img"
                alt="transaction"
                :src="require('~/assets/images/002-transaction.png')"
              />
              <a href="/TransactionHistory" class="header-menu-text"
                >Транзакции</a
              >
            </a>
          </li>
        </ul>
        <div
          class="header-menu-underline-transaction"
          :class="{
            'header-menu-underline-transaction_actived':
              selectLine == 'transaction',
          }"
        ></div>
      </div>

      <div class="header-notifications-container">
        <a href="">
          <img
            class="notifications"
            alt="notifications"
            :src="require('~/assets/images/notifications.png')"
          />
        </a>
        <a href="">
          <img
            class="alerts"
            alt="alerts"
            :src="require('~/assets/images/alerts.png')"
          />
        </a>
      </div>
    </section>
    <div class="mobile-header">
      <div class="mobile-header-content-container">
        <a href="/" class="header-logo-container">
          <img
            class="header-logo"
            alt="logo"
            :src="require('~/assets/images/logo.png')"
          />
          <img
            class="header-name"
            alt="logo-name"
            :src="require('~/assets/images/loance.png')"
          />
          <p class="keymat-logo">by Keymat</p>
        </a>
        <div class="header-notifications-container">
          <a href="">
            <img
              class="notifications"
              alt="notifications"
              :src="require('~/assets/images/notifications.png')"
            />
          </a>
          <a href="">
            <img
              class="alerts"
              alt="alerts"
              :src="require('~/assets/images/alerts.png')"
            />
          </a>
        </div>
        <div class="mobile-header-burger-menu">
          <div class="mobile-header-burger-line"></div>
          <div class="mobile-header-burger-line"></div>
          <div class="mobile-header-burger-line"></div>
        </div>
      </div>

      <div class="mobile-header-dropdown-container">
        <ul class="header-menu">
          <li>
            <a href="" class="header-link">
              <img
                class="header-menu-img_accounting"
                alt="accounting"
                :src="require('~/assets/images/001-accounting.png')"
              />
              <span class="header-menu-text">Займ</span>
            </a>
          </li>
          <li>
            <a href="" class="header-link">
              <img
                class="header-menu-img"
                alt="investments"
                :src="require('~/assets/images/001-return.png')"
              />
              <span class="header-menu-text">Инвестиции</span>
            </a>
          </li>
        </ul>
        <ul class="header-transaction">
          <li>
            <a href="" class="header-link header-link-transaction">
              <img
                class="header-menu-img"
                alt="transaction"
                :src="require('~/assets/images/002-transaction.png')"
              />
              <a href="/TransactionHistory" class="header-menu-text"
                >Транзакции</a
              >
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import "~assets/styles/components/Header/styles.scss";
</style>

<script>
export default {
  props: ["selectLine"],
  data() {
    return {
      options: [
        {
          id: "1",
          iconUrl: require("~/assets/images/account-button.png"),
        },
      ],
      selected: {
        id: "1",
        iconUrl: require("~/assets/images/account-button.png"),
      },
    };
  },
};
</script>