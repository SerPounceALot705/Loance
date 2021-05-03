<template>
  <div class="page">
    <Header />
    <section class="increase-in-deposit">
      <h3 class="increase-in-deposit-title">Увеличение залога</h3>
      <div v-if="!isIncrease" class="increase-in-deposit-container">
        <div class="transfer-of-assets-container transfer-of-assets-container_state">
          <div>
            <div class="replenishment-methods replenishment-methods_state">
              <h3 class="methods-subtitle">Выберите актив под залог:</h3>
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
                  #selected-option="{
                    iconUrl,
                    title,
                    subtitle,
                    amount,
                    balance,
                  }"
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
              <h3 class="replenishment-sum-title replenishment-sum-title_state">
                Введите сумму увеличения актива:
              </h3>
              <div class="replenishment-calc">
                <span class="usd">USD</span>
                <div class="transfer-cont">
                  <input type="text" class="calc-value" placeholder="14000.00">
                  <img
                    class="transfer"
                    alt="arrows"
                    :src="require('~/assets/images/transfer.png')"
                  />
                  <input type="text" placeholder="1.00000" class="calc-value">
                </div>
                <span class="btc">BTC</span>
              </div>
            </div>
          </div>
        </div>
        <table class="increase-in-deposit-table">
          <tr class="increase-in-deposit-table-line">
            <td class="increase-in-deposit-table-title">Оценочный подсчет</td>
            <td class="increase-in-deposit-table-increase">После увеличения</td>
            <td class="increase-in-deposit-table-current">Текущие</td>
          </tr>
          <tr>
            <td class="increase-in-deposit-table-subtitle">Залог</td>
            <td class="increase-in-deposit-table-increase-sum">&#36;1300.00</td>
            <td class="increase-in-deposit-table-current-sum">&#36;1200.00</td>
          </tr>
          <tr class="increase-in-deposit-table-line">
            <td class="increase-in-deposit-table-subtitle">Взятый кредит</td>
            <td class="increase-in-deposit-table-increase-sum">&#36;700.00</td>
            <td class="increase-in-deposit-table-current-sum">&#36;600.00</td>
          </tr>
          <tr class="increase-in-deposit-table-line">
            <td class="increase-in-deposit-table-subtitle">Доступный кредит</td>
            <td class="increase-in-deposit-table-increase-sum">&#36;700.00</td>
            <td class="increase-in-deposit-table-current-sum">&#36;600.00</td>
          </tr>
        </table>
        <button v-on:click="isIncrease = !isIncrease" class="increase-in-deposit-button">Увеличить актив</button>
      </div>

      <div v-if="isIncrease " class="transfer-request">
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
              />Bitcoin
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
          <div class="transfer-img">
            <img
              class="transfer-cheсkmark"
              alt="transfer-cheсkmark"
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
  },
};
</script>

<style>
@import "~assets/styles/Select/styles.scss";
@import "~assets/styles/TransferOfAssets/styles.scss";
@import "~assets/styles/IncreaseIndeposit/styles.scss";
</style>



