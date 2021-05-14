<template>
  <v-select
    v-model="selected"
    :options="options"
    :clearable="false"
    :searchable="false"
    :placeholder="'placeholder'"
    label="title"
    class="replenishment-select"
  >
    <template #selected-option="{ iconUrl, title, subtitle, amount, balance }">
      <div class="icon-container">
        <img :src="iconUrl" alt="icon" class="icon-img" />
      </div>
      <div class="select-info">
        <div class="select-info-container">
          <div class="select-info-title">{{ title }}</div>
          <div class="select-info-subtitle">{{ subtitle }}</div>
        </div>
        <div>
          <div class="select-info-title select-info-title_amount">
            {{ amount }}
          </div>
          <div class="select-info-subtitle">{{ balance }}</div>
        </div>
      </div>
    </template>
    <template v-slot:option="option">
      <img :src="option.iconUrl" alt="icon" class="icon-img" />
      <span>{{ option.title }}</span>
    </template>
  </v-select>
</template>

<style lang="scss">
@import "~assets/styles/_adaptive.scss";

.page {
  max-width: 1920px;
  margin: 0 auto;
  height: 1080px;
  background-image: url("~/assets/images/1080.png");
  background-repeat: no-repeat;

  @media #{$phone} {
    background-image: none;
  }
}

</style>

<script>
export default {
  data() {
    return {
      isIncrease: false,
      options: [
        {
          id: "1",
          iconUrl: require("~/assets/images/btc.png"),
          title: "BITCOIN",
          subtitle: "BTC",
          amount: "BTC 1.000023445",
          balance: "Текущий баланс:",
        },
      ],
      selected: {
        id: "1",
        iconUrl: require("~/assets/images/btc.png"),
        title: "BITCOIN",
        subtitle: "BTC",
        amount: "BTC 1.000023445",
        balance: "Текущий баланс:",
      },
    };
  }
};
</script>