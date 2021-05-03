<template>
  <div class="page">
    <Header />
    <section class="withdrawals-from-the-loan-office">
      <h3 class="withdrawals-from-the-loan-office-title">
        Вывод средств из кабинета займа
      </h3>
      <div class="withdrawals-from-the-loan-office-content-container">
        <div>
          <div v-if="isTransfer == false" class="withdrawals-from-the-loan-office-container">
            <span class="withdrawals-from-the-loan-office-subtitle"
              >Введите номер кошелька для вывода средств:</span
            >
            <input class="withdrawals-from-the-loan-office-input" />
            <div>
              <div
                class="replenishment-methods replenishment-methods_withdrawals-state"
              >
                <h3 class="methods-subtitle">
                  Выберите актив с которого хотите произвести вывод:
                </h3>
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
                <h3
                  class="replenishment-sum-title replenishment-sum-title_withdrawals-state"
                >
                  Введите сумму вывода:
                </h3>
                <div
                  class="replenishment-calc replenishment-calc_withdrawals-state"
                >
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
            <button class="withdrawals-from-the-loan-office-button">
              Заполнить доступной суммой баланса
            </button>
            <div class="withdrawals-from-the-loan-office-text-container">
              <span class="withdrawals-from-the-loan-office-text-title"
                >Комиссия на вывод:</span
              >
              <span class="withdrawals-from-the-loan-office-text"
                >Медиапланирование, как принято считать, стремительно изменяет
                отраслевой стандарт, невзирая на действия</span
              >
            </div>
            <button v-on:click="isTransfer = true" class="withdrawals-button">
              Вывести средства на кошелек
            </button>
          </div>
          <div v-if="isTransfer == true" class="transfer-request">
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
              <div class="transfer-of-assets-img">
                <img
                  class="transfer-of-assets-cheсkmark"
                  alt="transfer-of-assets-cheсkmark"
                  :src="require('~/assets/images/okbig.png')"
                />
              </div>
              <div class="transfer-of-assets-info-text-container">
                <span class="transfer-of-assets-info-text">
                  Перевод в систему инвестиций успешно воспроизведен, если
                  хотите перевести средства снова, нажмите ниже
                </span>
                <a class="transfer-of-assets-info-link">Перевести средства</a>
              </div>
            </div>
          </div>
        </div>

        <div class="withdrawals-from-the-loan-office-info-container">
          <div class="current-transactions">
            <span class="current-transactions-text">
              Текущие транзакции по выводу средств
            </span>
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
                <td class="table-info-type">Вывод средств</td>
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
                <td class="name-of-line name-of-line_withdrawals-status">
                  Статус
                </td>
                <td
                  class="table-info-status table-info-status_current-transactions-state"
                >
                  Отменено
                </td>
              </tr>
            </table>
            <a class="additional-info">Подробнее</a>
          </div>
          <div class="withdrawals-from-the-loan-office-info">
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
                <td class="table-info-type">Вывод средств</td>
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
                <td
                  class="name-of-line name-of-line_withdrawals-from-the-loan-office-info"
                >
                  Статус
                </td>
                <td
                  class="table-info-status table-info-status_withdrawals-from-the-loan-office-info-state"
                >
                  Успешно выведены
                </td>
              </tr>
            </table>
            <a class="additional-info">Подробнее</a>
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
@import "~assets/styles/WithdrawalsFromTheLoanOffice/styles.scss";
</style>