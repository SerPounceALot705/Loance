<template>
  <div class="page">
    <Header/>
    <section class="transfer-of-assets">
      <h3 class="transfer-of-assets-title">
        Перевод активов в инвестиционный кабинет
      </h3>
      <div v-if="!isTransfer" class="transfer-of-assets-container">
        <h3 class="transfer-of-assets-subtitle">Выберите актив для перевода</h3>
        <div>
          <div class="replenishment-methods">
            <h3 class="methods-subtitle">Переводы криптовалютой:</h3>
            <v-select
              v-model="selected"
              :options="options"
              :clearable="false"
              :searchable="false"
              :placeholder="'placeholder'"
              label="title"
              class="replenishment-select"
            >
              <template
                #selected-option="{ iconUrl, title, subtitle, amount, balance }"
              >
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
          </div>
          <div class="replenishment-sum">
            <h3 class="replenishment-sum-title">Введите сумму перевода</h3>
            <div class="replenishment-calc">
              <span class="usd">USD</span>
              <div class="transfer-cont">
                <input type="text" class="calc-value" placeholder="1400.00">
                <img
                  class="transfer"
                  alt="arrows"
                  :src="require('~/assets/images/transfer.png')"
                />
                <input type="text" class="calc-value" placeholder="1.0000000">
              </div>
              <span class="btc">BTC</span>
            </div>
          </div>
        </div>
        <button v-on:click="isTransfer = true" class="transfer-of-assets-button">Перевести инвестиции</button>
      </div>
      <div v-if="isTransfer" class="transfer-request">
        <h3 class="transfer-request-title">
          Заявка на перевод между кабинетами #10291571
        </h3>
        <table class="transfer-table-info">
          <tr>
            <td class="name-of-line">Дата/Время</td>
            <td class="table-info-time">08.07.2019 / 12:10</td>
          </tr>
          <tr>
            <td class="name-of-line">Номер</td>
            <td class="table-info-number">#340212</td>
          </tr>
          <tr>
            <td class="name-of-line">Тип операции</td>
            <td class="table-info-type">Перевод между кабинетами</td>
          </tr>
          <tr>
            <td class="name-of-line">Актив</td>
            <td class="table-info-currency">
              <img
                class="icon-img"
                alt="icon"
                :src="require('~/assets/images/btc.png')"
              />
              <p>Bitcoin</p>
            </td>
          </tr>
          <tr>
            <td class="name-of-line">Сумма</td>
            <td class="table-info-sum">1.002423748 BTC</td>
          </tr>
        </table>
        <table class="transfer-table-status">
          <tr>
            <td class="name-of-line name-of-line_status">Статус</td>
            <td class="table-info-status">Переведен</td>
          </tr>
        </table>
        <a class="additional-info">Подробнее</a>
        <div class="transfer-of-assets-info-container">
          <div class="transfer-of-assets-img">
            <img
              class="transfer-of-assets-cheсkmark"
              alt="transfer-of-assets-cheсkmark"
              :src="require('~/assets/images/okbig.png')"
            />
          </div>
          <div class="transfer-of-assets-info-text-container">
            <span class="transfer-of-assets-info-text">
              Перевод в систему инвестиций успешно воспроизведен, если хотите
              перевести средства снова, нажмите ниже
            </span>
            <a class="transfer-of-assets-info-link">Перевести средства</a>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "BalanceReplenishment",
  data() {
    return {
      isTransfer: false,
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
  },
};
</script>

<style>
@import "~assets/styles/Select/styles.scss";
@import "~assets/styles/TransferOfAssets/styles.scss";
@import "~assets/styles/IncreaseIndeposit/styles.scss";
</style>