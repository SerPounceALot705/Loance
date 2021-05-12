<template>
  <div class="page">
    <Header :isSubtitle="true" selectLine="default"/>
    <section class="loanscreen">
      <div class="loanscreen-content-container">
        <div class="loanScreen-container">
          <div class="available-loan-amount">
            <h3 class="available-loan-amount-title">Кредитное обеспечение</h3>
            <span class="available-credit-title">Доступный кредит</span>
            <span class="available-credit-total">&#36;600.00</span>
          </div>
          <div class="taken-credit-container">
            <span class="taken-credit-title">Взятый кредит</span>
            <span class="taken-credit-total">&#36;600.00</span>
          </div>
        </div>
        <div class="withdrawal-of-funds-container">
          <h3 class="withdrawal-of-funds-title">
            Вывод средств с доступного кредитного обеспечения
          </h3>
          <div class="withdrawal-of-funds-button">
            <img
              class="withdrawal-of-funds-button-img"
              :src="require('~/assets/images/download.png')"
              alt="download-icon"
            />
            <span class="withdrawal-of-funds-button-text">Вывод средств</span>
          </div>
          <h3 class="repayment-of-credit-title">
            Погашение кредитного обеспечения
            <img
              class="repayment-of-credit-title-information"
              :src="require('~/assets/images/information.png')"
              alt="information-icon"
            />
          </h3>

          <div class="repayment-of-credit-button">
            <img
              class="repayment-of-credit-button-img"
              :src="require('~/assets/images/upload.png')"
              alt="upload-icon"
            />
            <a href="/LoanRepayment" class="repayment-of-credit-button-text"
              >Погашение долга</a
            >
          </div>
        </div>
        <div class="affiliate-program-container">
          <h3 class="affiliate-program-title">Партнерская программа</h3>
          <span class="affiliate-program-text">Ваша партнерская ссылка:</span>
          <input
            class="affiliate-program-input"
            placeholder="5124foofa22o44odd11o"
            ref="affiliate"
          />
          <div class="copy" v-on:click="copy"></div>
          <button class="affiliate-program-button">
            Подробнее о партнерской программе
          </button>
        </div>
      </div>
      <div class="loanscreen-content-container">
        <div class="assets-container">
          <h3 class="assets-title">Активы</h3>
          <div class="assets-table-titles-container">
            <span>Кошелек с валютой</span>
            <span
              >Баланс
              <p>кошелька</p></span
            >
            <span>
              Рыночная стоимость
              <img
                class="assets-table-title-information-img"
                :src="require('~/assets/images/information.png')"
                alt="information-icon"
              />
            </span>
            <span
              >Кредитное обеспечение
              <img
                class="assets-table-title-information-credit-img"
                :src="require('~/assets/images/information.png')"
                alt="information-icon"
              />
            </span>
            <span
              >Увеличить актив займа
              <img
                class="assets-table-title-information-asset-img"
                :src="require('~/assets/images/information.png')"
                alt="information-icon"
            /></span>
          </div>
          <div class="assets-table-item-container">
            <div class="assets-table-item-current-container">
              <img :src="require('~/assets/images/btc.png')" />
              <span>Bitcoin</span>
            </div>
            <span class="assets-table-item-total">BTC 1.000023</span>
            <span class="assets-table-item-sum">&#36;62000</span>
            <span class="assets-table-item-sum">&#36;300.00</span>
            <div class="assets-table-item-button">+</div>
            <div class="assets-table-item-score"></div>
          </div>
          <div class="assets-table-item-container">
            <div class="assets-table-item-current-container">
              <img :src="require('~/assets/images/Etherium.png')" />
              <span>Etherium</span>
            </div>
            <span class="assets-table-item-total">ETH 1.000023</span>
            <span class="assets-table-item-sum">&#36;2000</span>
            <span class="assets-table-item-sum">&#36;200.00</span>
            <div class="assets-table-item-button">+</div>
            <div
              class="assets-table-item-score assets-table-item-score_blue"
            ></div>
          </div>
          <div class="assets-table-item-container">
            <div class="assets-table-item-current-container">
              <img :src="require('~/assets/images/keymat.png')" />
              <span>Keymat Token</span>
            </div>
            <span class="assets-table-item-total">KMX 20.00</span>
            <span class="assets-table-item-sum">&#36;200</span>
            <span class="assets-table-item-sum">&#36;100.00</span>
            <div class="assets-table-item-button">+</div>
            <div
              class="assets-table-item-score assets-table-item-score_green"
            ></div>
          </div>
          <div class="assets-table-item-container">
            <div
              class="assets-table-item-current-container assets-table-item-current-container_inactive"
            >
              <div class="assets-table-item-current-inactive"></div>
              <span>Binance</span>
            </div>
            <span
              class="assets-table-item-total assets-table-item-total_inactive"
              >BNB 0.000000000</span
            >
            <span class="assets-table-item-sum assets-table-item-sum_inactive"
              >&#36;0.00</span
            >
            <span class="assets-table-item-sum assets-table-item-sum_inactive"
              >&#36;0.00</span
            >
            <div class="assets-table-item-button">+</div>
          </div>
          <div class="assets-table-item-container">
            <div
              class="assets-table-item-current-container assets-table-item-current-container_inactive"
            >
              <div class="assets-table-item-current-inactive"></div>
              <span>Binance</span>
            </div>
            <span
              class="assets-table-item-total assets-table-item-total_inactive"
              >BNB 0.000000000</span
            >
            <span class="assets-table-item-sum assets-table-item-sum_inactive"
              >&#36;0.00</span
            >
            <span class="assets-table-item-sum assets-table-item-sum_inactive"
              >&#36;0.00</span
            >
            <div class="assets-table-item-button">+</div>
          </div>
        </div>
        <div class="deposit-container">
          <div class="deposit-score-container">
            <div class="score-item-green"></div>
            <div class="score-item-blue"></div>
            <div class="score-item-red"></div>
          </div>
          <span class="deposit-text"
            >Залог
            <p>(от рыночной стоимости)</p></span
          >
          <span class="deposit-total">&#36;1200.00</span>
          <span class="deposit-earned"
            >Заработано за
            <p>партнерскую программу</p></span
          >
          <span class="deposit-erned-total">&#36;103.00</span>
          <span class="deposit-actual"
            >Текущий
            <p>непогашенный займ</p></span
          >
          <span class="deposit-erned-total">&#36;0.00</span>
          <button class="deposit-top-up-balance-button">
            Пополнить баланс
          </button>
          <button class="deposit-transfer-balance-button">
            Перевести баланс в инвестиционный
          </button>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    copy(event) {
      let value = this.$refs.affiliate;
      value.select();
      document.execCommand("copy");
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
  
  @media #{$phone} {
    background-image: none;
    height: auto;
  }
}
</style>