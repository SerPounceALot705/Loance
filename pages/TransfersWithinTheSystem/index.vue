<template>
  <div class="page">
    <Header />
    <section class="transfers-within-the-system">
      <h3 class="transfers-within-the-system-title">Перевод внутри системы</h3>
      <div
        v-if="selectPage == 'transfers'"
        class="transfers-within-the-system-content-container"
      >
        <div class="transfers-within-the-system-container">
          <div class="content-container">
            <h3 class="transfers-within-the-system-subtitle">
              Оформление перевода внутри системы
            </h3>
            <span class="transfers-within-the-system-text">
              Введите логин участника Loance для перевода
            </span>
            <div class="transfers-within-the-system-input-container">
              <input class="transfers-within-the-system-input" />
              <span class="transfers-within-the-system-input-text"
                >Данный пользователь существует в системе</span
              >
            </div>
          </div>

          <div class="transfer-repl-methods-container">
            <div class="replenishment-methods">
              <h3 class="methods-subtitle">
                Выберите актив для перевода внутри системы:
              </h3>
              <Select />
            </div>
            <div class="replenishment-sum">
              <h3 class="replenishment-sum-title">Введите сумму перевода</h3>
              <div class="replenishment-calc">
                <span class="usd">USD</span>
                <div class="transfer-cont">
                  <input type="text" class="calc-value" placeholder="1400.00" />
                  <img
                    class="transfer"
                    alt="arrows"
                    :src="require('~/assets/images/transfer.png')"
                  />
                  <input
                    type="text"
                    class="calc-value"
                    placeholder="1.000000"
                  />
                </div>
                <span class="btc">BTC</span>
              </div>
            </div>
          </div>
          <div class="transfers-within-the-system-button-container">
            <button
              v-on:click="selectPage = 'verify'"
              class="transfers-within-the-system-button"
            >
              Перевести участнику
            </button>
          </div>
        </div>
        <div class="top-up-balance top-up-balance_transfers-within-the-system">
          <span class="top-up-balance-text">Не хватает баланса?</span>
          <button class="top-up-balance-button">Пополнить баланс</button>
        </div>
      </div>
      <div v-if="selectPage == 'verify'" class="verify-data">
        <span class="verify-data-text">Сверьте данные для перевода</span>
        <table>
          <tr>
            <td class="verify-data-table-title">Логин</td>
            <td class="verify-data-table-value">uooyyqq</td>
          </tr>
          <tr>
            <td class="verify-data-table-title">Актив</td>
            <td class="verify-data-table-value">
              <img
                class="verify-data-table-img"
                alt="verify-data-img"
                :src="require('~/assets/images/btc.png')"
              />
              <p>Bitcoin</p>
            </td>
          </tr>
          <tr>
            <td class="verify-data-table-title">Сумма</td>
            <td class="verify-data-table-value">
              1.002423748 BTC / 1400.00 LUD
            </td>
          </tr>
        </table>
        <div class="verify-data-button-container">
          <button
            v-on:click="selectPage = 'transferData'"
            class="verify-data-button-submit"
          >
            Все верно, открыть
          </button>
          <button
            v-on:click="selectPage = 'transfers'"
            class="verify-data-button-reject"
          >
            Отклонить
          </button>
        </div>
      </div>
      <div v-if="selectPage == 'transferData'" class="transfer-data">
        <span class="transfer-data-text">Данные перевода</span>
        <table>
          <tr>
            <td class="verify-data-table-title">Логин</td>
            <td class="verify-data-table-value">uooyyqq</td>
          </tr>
          <tr>
            <td class="verify-data-table-title">Актив</td>
            <td class="verify-data-table-value">
              <img
                class="verify-data-table-img"
                alt="verify-data-img"
                :src="require('~/assets/images/btc.png')"
              />Bitcoin
            </td>
          </tr>
          <tr>
            <td class="verify-data-table-title">Сумма</td>
            <td class="verify-data-table-value">
              1.002423748 BTC / 1400.00 LUD
            </td>
          </tr>
        </table>
        <div
          class="transfer-of-assets-info-container transfer-of-assets-info-container_verify-data"
        >
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
            <a href="/TransactionHistory" class="transfer-of-assets-info-link"
              >Перевести средства</a
            >
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
      selectPage: "transfers",
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
</style>