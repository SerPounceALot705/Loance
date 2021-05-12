<template>
  <div class="page">
    <Header />

    <section class="replenishment">
      <h3 class="replenishment-title">Пополнение баланса</h3>
      <div>
        <div class="replenishment-container">
          <div class="methods-container">
            <div class="replenishment-methods">
              <h3 class="methods-title">Выберите способ пополнения</h3>
              <h3 class="methods-subtitle">Переводы криптовалютой:</h3>
              <Select />
            </div>
            <div class="replenishment-sum">
              <h3 class="replenishment-sum-title">Введите сумму пополнения</h3>
              <div class="replenishment-calc">
                <span class="usd">USD</span>
                <div class="transfer-cont">
                  <input type="text" class="calc-value" placeholder="0.00" />
                  <img
                    class="transfer"
                    alt="arrows"
                    :src="require('~/assets/images/transfer.png')"
                  />
                  <input
                    type="text"
                    class="calc-value"
                    placeholder="0.0000000"
                  />
                </div>
                <span class="btc">BTC</span>
              </div>
            </div>
            <button
              v-if="!isUpBalance"
              v-on:click="onUpBalance()"
              class="replenishment-button"
            >
              Пополнить баланс
            </button>
            <div v-if="isUpBalance" class="info-box">
              <div class="circle">
                <img
                  class="circle-checkmark"
                  alt="circle-checkmark"
                  :src="require('~/assets/images/okbig.png')"
                />
              </div>
              <div class="info-box-container">
                <span class="info-text"
                  >Посмотрите информацию о платеже и закончите процесс
                  пополнения баланса</span
                >
                <a class="repl-link">Пополнить снова</a>
              </div>
            </div>
          </div>

          <div>
            <h3 class="transfers-subtitle">Электронные переводы:</h3>
            <div
              v-for="item in translations"
              :key="item.id"
              v-on:click="onSelectTranslations(item.value)"
              class="transfer-item"
              :class="{
                'transfer-item-select': selectTranslations == item.value,
              }"
            >
              <div class="img-container">
                <img
                  class="transfer-item-icon"
                  alt="transfer-icon"
                  :src="item.iconUrl"
                />
              </div>
              <div class="transfer-container">
                <span class="transfer-title-item">{{ item.title }}</span>
                <span class="transfer-subtitle-item">{{ item.subTitle }}</span>
              </div>
            </div>
          </div>
        </div>
        <div
          v-if="selectTranslations == 'payeer' && isUpBalance"
          class="payment-information"
        >
          <div class="payment-information-container">
            <div class="payment-info-container">
              <div class="payment-information-container-item">
                <span class="payment-information-title"
                  >Информация о платеже
                  <p class="payment-information-number">#42534</p></span
                >
              </div>
              <div class="payment-information-container-item">
                <span class="payment-information-text"
                  >Осталось времени на платеж:</span
                >
                <span class="time">0 мин : 59 мин</span>
              </div>
            </div>
            <div class="payment-information-container-history">
              <a href="/TransactionHistory" class="payment-transaction-history"
                >История транзакций</a
              >
              <span class="time">08.07.2019 18:16</span>
            </div>
          </div>
          <div class="payment-information-container">
            <div class="payment-information-amount">
              <div>
                <h3 class="payment-information-text-sum">Сумма платежа:</h3>
                <div class="payment-information-amount-container">
                  <span class="payment-information-amount-sum">100.00</span>
                  <span class="currency-type">USD</span>
                </div>
              </div>
              <div>
                <h3 class="payment-information-text-sum">
                  Счет пополнится на:
                </h3>
                <div class="payment-information-amount-container">
                  <span class="payment-information-amount-sum">100.00</span>
                  <span class="currency-type">USD</span>
                </div>
              </div>
            </div>
            <div class="payment-information-email">
              <h3 class="payment-information-text">
                Адрес эл. почты для отправки платежа:
              </h3>
              <input
                class="payment-information-input"
                placeholder="loance@mail.ru"
                type="email"
              />
              <div class="payment-status">
                <span class="payment-information-text">Статус платежа:</span>
                <span class="payment-status-text">
                  {{ waitTranslationsText }}</span
                >
                <a class="repl-link">Отменить заявку</a>
              </div>
            </div>
          </div>
          <div class="payment-information-container">
            <div class="payment-information-alert">
              <img
                class="alert-icon"
                alt="alert-icon"
                :src="require('~/assets/images/alert.png')"
              />
              <span>
                <p class="alert-text">Убедитесь, что заявка оплачена.</p>
                <p class="alert-text">
                  Только после этого нажмите кнопку "Я оплатил заявку".
                </p>
              </span>
            </div>
            <button
              v-on:click="onPaid()"
              :class="{
                'pay-button-submit_state': isPaid,
                'pay-button-submit': !isPaid,
              }"
            >
              {{ paidButtonText }}
            </button>
          </div>
        </div>
        <div
          v-if="selectTranslations != 'payeer' && isUpBalance"
          class="payment-information"
        >
          <div class="payment-information-container">
            <div class="payment-info-container">
              <div class="payment-information-container-item">
                <span class="payment-information-title"
                  >Информация о платеже
                  <p class="payment-information-number">#42534</p>
                </span>
              </div>
              <div class="payment-information-container-item">
                <span class="payment-information-text"
                  >Осталось времени на платеж:</span
                >
                <span class="time">0 мин : 59 мин</span>
              </div>
            </div>
            <div class="payment-information-container-history">
              <a class="payment-transaction-history">История транзакций</a>
              <span class="time">08.07.2019 18:16</span>
            </div>
          </div>
          <div
            class="payment-information-container payment-information-container_state"
          >
            <div class="qr-code-container">
              <img
                class="qr-code"
                alt="qr-code"
                :src="require('~/assets/images/qr-code.png')"
              />
            </div>

            <div
              class="payment-information-amount payment-information-amount_state"
            >
              <div>
                <h3 class="payment-information-text-sum">Сумма платежа:</h3>
                <div
                  class="payment-information-amount-container payment-information-amount-container_state"
                >
                  <span
                    class="payment-information-amount-sum payment-information-amount-sum_state"
                    >0.000002315</span
                  >
                  <span class="currency-type">BTC</span>
                </div>
              </div>
              <div>
                <h3 class="payment-information-text-sum">
                  Счет пополнится на:
                </h3>
                <div
                  class="payment-information-amount-container payment-information-amount-container_state"
                >
                  <span
                    class="payment-information-amount-sum payment-information-amount-sum_state"
                    >0.000002315</span
                  >
                  <span class="currency-type">BTC</span>
                </div>
              </div>
            </div>
            <div class="payment-information-email">
              <h3 class="payment-information-text">
                Кошелек для отправки BTC:
              </h3>
              <input
                class="payment-information-input"
                placeholder="i1j24uh1uhu2uhuhu1uh5uho"
                type="email"
              />
              <div class="payment-status payment-status_state">
                <span class="payment-information-text">Статус платежа:</span>
                <span class="payment-status-text"> В процессе </span>
                <a class="repl-link">Отменить заявку</a>
              </div>
            </div>
          </div>
          <div class="payment-information-container">
            <div class="payment-information-alert">
              <img
                class="alert-icon"
                alt="alert-icon"
                :src="require('~/assets/images/alert.png')"
              />
              <span>
                <p class="alert-text">
                  Сумма платежа должна совпадать с суммой, указанной в заявке,
                  иначе, средства могут быть не зачислены на Ваш баланс.
                </p>
              </span>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Header from "~/components/Header.vue";
import Select from "~/components/Select.vue";
export default {
  name: "BalanceReplenishment",
  components: { Header, Select },
  data() {
    return {
      selectTranslations: "",
      isUpBalance: false,
      isPaid: false,
      paidButtonText: "Я оплатил",
      waitTranslationsText: "Ожидание оплаты",
      translations: [
        {
          id: 1,
          iconUrl: require("~/assets/images/payeer.png"),
          title: "PAYEER",
          subTitle: "Ewallet",
          value: "payeer",
        },
        {
          id: 2,
          iconUrl: require("~/assets/images/pm.png"),
          title: "PERFECT-MONEY",
          subTitle: "Ewallet",
          value: "perfectMony",
        },
        {
          id: 3,
          iconUrl: require("~/assets/images/a.png"),
          title: "ADVCASH",
          subTitle: "Ewallet",
          value: "advcash",
        },
      ],
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
  methods: {
    onSelectTranslations: function (value) {
      this.selectTranslations = value;
    },
    onUpBalance: function () {
      if (this.selectTranslations != "") {
        this.isUpBalance = true;
      } else {
        alert("Необходимо выбрать способ перевода");
      }
    },
    onPaid: function () {
      this.isPaid = true;
      this.paidButtonText = !this.isPaid ? "Я оплатил" : "Спасибо";
      this.waitTranslationsText = !this.isPaid
        ? "Ожидание оплаты"
        : "Обрабатывается";
    },
  },
};
</script>

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
    margin: 0 auto;
    height: auto;
  }
}
</style>