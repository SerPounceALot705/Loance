<template>
  <div class="page">
    <Header />
    <section class="loan-repayment">
      <h3 class="loan-repayment-title">
        Гибкая выплата кредитного обеспечения
      </h3>
      <div class="loan-repayment-content-container">
        <div class="methods-of-repayment">
          <span class="methods-of-repayment-title">Способы погашения</span>
          <input
            class="methods-of-repayment-input"
            placeholder="Поиск валюты"
          />
          <div class="corusel">
            <VueSlickCarousel v-bind="settings">
              <div
                v-for="item in items"
                :key="item.id"
                class="currency"
                :class="{ currency_actived: select.id == item.id }"
                v-on:click="select = item"
              >
                <span class="abbreviation"
                  >{{ item.title }}
                  <p class="type-of-currency">{{ item.subTitle }}</p>
                </span>
              </div>
            </VueSlickCarousel>
          </div>
          <table v-if="select.id != 0" class="about-currency">
            <tr>
              <td width="125px" class="about-currency-title">Кошелек</td>
              <td class="about-currency-title">Баланс</td>
              <td class="about-currency-title">
                Рыночная стоимость
                <a
                  ><img
                    :src="require('~/assets/images/information.png')"
                    alt="information-icon"
                /></a>
              </td>
            </tr>
            <tr>
              <td class="about-currency-name">
                <img :src="select.icon" alt="currency-colour-icon" />
                <p class="about-currency-name-text">{{ select.subTitle }}</p>
              </td>
              <td width="125px" class="about-currency-sum">
                BTC {{ select.btcPrice }}
              </td>
              <td width="150px" class="about-currency-price">
                &#36;{{ select.utdPrice }}
              </td>
            </tr>
          </table>
          <span class="repayment-amount"
            >Сумма платежа по погашению в криптовалюте:</span
          >
          <input class="repayment-amount-input" />
          <span class="estimated-repayment-amount"
            >Оценочная сумма платежа по погашению</span
          >
          <input class="estimated-repayment-amount-input" />
          <button class="repayment-button">Погасить</button>
          <table class="estimated-count-table">
            <tr>
              <td class="estimated-count-title" width="200px">
                Оценочный подсчет
              </td>
              <td class="after-maturity_title">После погашения</td>
              <td class="earlier_title">Ранее</td>
            </tr>
            <tr>
              <td class="estimated-count-subtitle" width="200px">Все активы</td>
              <td class="after-maturity">&#36;0.00</td>
              <td class="earlier">&#36;0.00</td>
            </tr>
            <tr>
              <td class="estimated-count-subtitle" width="200px">
                Кредитное обеспечение
              </td>
              <td class="after-maturity">&#36;0.00</td>
              <td class="earlier">&#36;0.00</td>
            </tr>
            <tr>
              <td class="estimated-count-subtitle" width="200px">
                Непогашенный займ
              </td>
              <td class="after-maturity">&#36;0.00</td>
              <td class="earlier">&#36;0.00</td>
            </tr>
            <tr>
              <td class="estimated-count-subtitle" width="200px">
                Доступное кредитное обеспечение
              </td>
              <td class="after-maturity">&#36;0.00</td>
              <td class="earlier">&#36;0.00</td>
            </tr>
          </table>
        </div>
        <div class="current-loan">
          <div class="current-loan-container">
            <span class="current-loan-title">Текущий непогашенный займ</span>
            <span class="current-loan-sum">&#36;200.00</span>
          </div>
          <div class="top-up-balance top-up-balance_current-loan">
            <span class="top-up-balance-text">Не хватает баланса?</span>
            <a href="/BalanceReplenishment" class="top-up-balance-button">Пополнить баланс</a>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>

  import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
export default {
  name: "LoanRepayment",
  data() {
    return {
      settings: {
        dots: false,
        focusOnSelect: true,
        infinite: true,
        speed: 500,
        slidesToShow: 5,
        slidesToScroll: 3,
        touchThreshold: 5,
      },
      items: [
        {
          id: 1,
          title: "BTC",
          subTitle: "Bitcoin",
          btcPrice: "1.000023445",
          utdPrice: "1320.00",
          icon: require("~/assets/images/elipse.png"),
        },
        {
          id: 2,
          title: "ETH",
          subTitle: "Ether",
          btcPrice: "1.000023445",
          utdPrice: "1320.00",
          icon: require("~/assets/images/elipse.png"),
        },
        {
          id: 3,
          title: "USD",
          subTitle: "US Dollar",
          btcPrice: "1.000023445",
          utdPrice: "1320.00",
          icon: require("~/assets/images/elipse.png"),
        },
        {
          id: 4,
          title: "EUR",
          subTitle: "Euro",
          btcPrice: "1.000023445",
          utdPrice: "1320.00",
          icon: require("~/assets/images/elipse.png"),
        },
        {
          id: 5,
          title: "USDT",
          subTitle: "Tether Omni",
          btcPrice: "1.000023445",
          utdPrice: "1320.00",
          icon: require("~/assets/images/elipse.png"),
        },
        {
          id: 6,
          title: "GBP",
          subTitle: "Pounds Sterling",
          btcPrice: "1.000023445",
          utdPrice: "1320.00",
          icon: require("~/assets/images/elipse.png"),
        },
      ],
      select: {
        id: 0,
      },
    };
  },
};
</script>

<style lang="scss">
@import "~assets/styles/LoanRepayment/styles.scss";
</style>