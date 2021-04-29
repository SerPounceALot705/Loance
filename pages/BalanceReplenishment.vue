<template>
  <div class="page">
    <Header />

    <section class="replenishment">
      <h3 class="replenishment-title">Пополнение баланса</h3>
      <div>
        <div class="replenishment-container">
          <div>
            <div class="replenishment-methods">
              <h3 class="methods-title">Выберите способ пополнения</h3>
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
              <h3 class="replenishment-sum-title">Введите сумму пополнения</h3>
              <div class="replenishment-calc">
                <span class="usd">USD</span>
                <div class="transfer-cont">
                  <span class="calc-value">0.00</span>
                  <img
                    class="transfer"
                    alt="arrows"
                    src="../assets/images/transfer.png"
                  />
                  <span class="calc-value">0.000000000</span>
                </div>
                <span class="btc">BTC</span>
              </div>
            </div>
            <button class="replenishment-button">Пополнить баланс</button>
            <div class="info-box">
              <div class="circle">
                <img
                  class="circle-checkmark"
                  alt="circle-checkmark"
                  src="../assets/images/okbig.png"
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
            <div class="transfer-item">
              <div class="img-container">
                <img
                  class="transfer-item-icon"
                  alt="transfer-icon"
                  src="../assets/images/payeer.png"
                />
              </div>
              <div class="transfer-container">
                <span class="transfer-title-item">PAYEER</span>
                <span class="transfer-subtitle-item">Ewallet</span>
              </div>
            </div>
            <div class="transfer-item">
              <div class="img-container">
                <img
                  class="transfer-item-icon"
                  alt="transfer-icon"
                  src="../assets/images/pm.png"
                />
              </div>
              <div class="transfer-container">
                <span class="transfer-title-item">PERFECT-MONEY</span>
                <span class="transfer-subtitle-item">Ewallet</span>
              </div>
            </div>
            <div class="transfer-item">
              <div class="img-container">
                <img
                  class="transfer-item-icon"
                  alt="transfer-icon"
                  src="../assets/images/a.png"
                />
              </div>
              <div class="transfer-container">
                <span class="transfer-title-item">ADVCASH</span>
                <span class="transfer-subtitle-item">Ewallet</span>
              </div>
            </div>
          </div>
        </div>
        <div class="payment-information">
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
              <a class="transaction-history">История транзакций</a>
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
                <span class="payment-status-text">Ожидание оплаты</span>
                <a class="repl-link">Отменить заявку</a>
              </div>
            </div>
          </div>
          <div class="payment-information-container">
            <div class="payment-information-alert">
              <img
                class="alert-icon"
                alt="alert-icon"
                src="../assets/images/alert.png"
              />
              <span>
                <p class="alert-text">Убедитесь, что заявка оплачена.</p>
                <p class="alert-text">
                  Только после этого нажмите кнопку "Я оплатил заявку".
                </p>
              </span>
            </div>
            <button class="pay-button-submit">Я оплатил</button>
          </div>
        </div>
        <div class="payment-information">
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
              <a class="transaction-history">История транзакций</a>
              <span class="time">08.07.2019 18:16</span>
            </div>
          </div>
          <div
            class="payment-information-container payment-information-container_state"
          >
            <img
              class="qr-code"
              alt="qr-code"
              src="../assets/images/qr-code.png"
            />
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
                <span class="payment-status-text">Ожидание оплаты</span>
                <a class="repl-link">Отменить заявку</a>
              </div>
            </div>
          </div>
          <div class="payment-information-container">
            <div class="payment-information-alert">
              <img
                class="alert-icon"
                alt="alert-icon"
                src="../assets/images/alert.png"
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
        <div class="payment-information">
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
              <a class="transaction-history">История транзакций</a>
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
                <span class="payment-status-text">Ожидание оплаты</span>
                <a class="repl-link">Отменить заявку</a>
              </div>
            </div>
          </div>
          <div class="payment-information-container">
            <div class="payment-information-alert">
              <img
                class="alert-icon"
                alt="alert-icon"
                src="../assets/images/alert.png"
              />
              <span>
                <p class="alert-text">Убедитесь, что заявка оплачена.</p>
                <p class="alert-text">
                  Только после этого нажмите кнопку "Я оплатил заявку".
                </p>
              </span>
            </div>
            <button class="pay-button-submit pay-button-submit_state">
              Спасибо
            </button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>


<script>
import Header from "../components/Header.vue";
export default {
  name: "BalanceReplenishment",
  components: { Header },
  data() {
    return {
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
.page {
  width: 100%;
  height: 1080px;
  max-width: 100%;
  background: #e9ecf1;
  background-image: url("../assets/images/Web 1920 – 1.png");
}

.replenishment-methods {
  margin-bottom: 48px;
}

.replenishment-title {
  height: 30px;
  font-family: "Montserrat";
  font-size: 25px;
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-bottom: 37px;
}

.arrows {
  display: flex;
  flex-direction: column;
}

.replenishment {
  width: 70%;
  margin: 0 auto;
  margin-top: 45px;
}

.replenishment-container {
  display: flex;
  flex-direction: row;
  width: 730px;
  height: auto;
  padding: 32px;
  border-radius: 15px;
  background-color: #ffffff;
  justify-content: space-around;
}

.methods-title {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.31;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-bottom: 25px;
  margin-top: 36px;
}

.methods-subtitle {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-bottom: 22px;
}

.replenishment-select {
  width: 380px;
  height: 50px;
  border-radius: 4px;
  border: solid 1px #e8ecf3;
  background-color: #ffffff;
}

.replenishment-select .vs__dropdown-toggle {
  border: none;
}

.replenishment-select .vs__selected-options {
  height: 50px;
}

.icon-img {
  width: 18px;
  height: 18px;
  object-fit: contain;
}

.icon-container {
  display: flex;
  align-items: center;
  justify-content: center;
  border-right: 2px solid #e9ecf1;
  margin-right: 17px;
  padding-right: 22px;
  margin-left: 17px;
  padding-top: 10px;
  padding-bottom: 10px;
}

.replenishment-select .vs__selected {
  margin: 0;
  padding: 0;
}

.replenishment-select .vs__selected-options {
  padding: 0;
}

.replenishment-select .vs__actions {
  padding: 2px 25px 0 3px;
}

.select-info-title {
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  height: 15px;
  margin-bottom: 2px;
}

.select-info-subtitle {
  font-family: "Montserrat";
  font-size: 8px;
  font-weight: 300;
  font-stretch: normal;
  font-style: normal;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  height: 9px;
}

.select-info-title_amount {
  font-weight: 500;
}

.select-info-container {
  margin-right: 50px;
}

.select-info {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.replenishment-sum-title {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.31;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-bottom: 13px;
}

.replenishment-calc {
  display: flex;
  flex-direction: row;
  width: 380px;
  height: 60px;
  margin: 13px 0 0;
  padding: 10px 0;
  border-radius: 10px;
  border: solid 1px #e8ecf3;
  background-color: #ffffff;
  justify-content: space-between;
  margin-bottom: 46px;
}

.usd {
  padding-top: 11px;
  margin-left: 17px;
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.67;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  border-right: 2px solid #e9ecf1;
  padding-right: 20px;
}

.calc-value {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 300;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.transfer {
  width: 8px;
  height: 8px;
  object-fit: contain;
  margin: 5px 15px 5px;
}

.transfer-cont {
  align-items: center;
  display: flex;
}

.btc {
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.67;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  padding-top: 11px;
  margin-right: 17px;
  padding-left: 20px;
  border-left: 2px solid #e9ecf1;
}

.replenishment-button {
  width: 380px;
  height: 61px;
  border-radius: 10px;
  border: solid 1px #8d75f8;
  background-color: #ffffff;
  margin-bottom: 64px;
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.36;
  letter-spacing: normal;
  text-align: center;
  color: #8d75f8;
  cursor: pointer;
}

.replenishment-button:hover {
  background: rgb(140, 116, 247);
  background: linear-gradient(
    90deg,
    rgba(140, 116, 247, 1) 23%,
    rgba(140, 116, 247, 0.9332107843137255) 48%,
    rgba(186, 175, 235, 0.865983893557423) 79%
  );
  color: #ffffff;
  transition: 0.3s ease-in-out;
}

.transfers-subtitle {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-top: 80px;
  margin-bottom: 22px;
}

.transfer-item {
  width: 223px;
  height: 50px;
  margin-bottom: 18px;
  padding: 6px 21px;
  border-radius: 4px;
  box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.16);
  background-color: #ffffff;
  display: flex;
  align-items: center;
  cursor: pointer;
}

.transfer-item:hover {
  border: 1px solid #8c74f7;
}

.transfer-container {
  border-left: 2px solid #e9ecf1;
  display: flex;
  flex-direction: column;
  margin-left: 15px;
  padding-left: 15px;
}

.transfer-title-item {
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.67;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.transfer-subtitle-item {
  font-family: "Montserrat";
  font-size: 7px;
  font-weight: 300;
  font-stretch: normal;
  font-style: normal;
  line-height: 2.86;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.img-container {
  width: 36px;
  display: flex;
  justify-content: center;
}

.info-box {
  display: flex;
  flex-direction: row;
  margin-bottom: 51px;
}

.circle {
  width: 60px;
  height: 60px;
  background-color: #c5e1a5;
  border-radius: 50%;
  margin-right: 52px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.info-box-container {
  display: flex;
  flex-direction: column;
}

.info-text {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.46;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  width: 281px;
  margin-bottom: 6px;
}

.repl-link {
  font-family: "Montserrat";
  font-size: 10px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.9;
  letter-spacing: normal;
  text-align: left;
  color: #919aa7;
  text-decoration: underline;
}

.payment-information {
  display: flex;
  flex-direction: column;
  border-radius: 15px;
  background-color: #ffffff;
  width: 730px;
  padding: 32px;
  border-top-width: 1px;
  border-top-color: #919aa7;
  border-top-style: dashed;
}

.payment-information-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-bottom: 22px;
}

.payment-information-container_state {
  justify-content: flex-start;
}

.payment-information-container-item {
  display: flex;
  flex-direction: row;
}

.payment-information-title {
  display: flex;
  flex-direction: row;
}

.payment-information-container-history {
  display: flex;
  flex-direction: column;
}

.payment-information-title {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.31;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-bottom: 7px;
}

.payment-information-number {
  font-family: "Montserrat";
  font-size: 10px;
  font-weight: 300;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.9;
  letter-spacing: normal;
  text-align: left;
  color: #919aa7;
  margin-left: 8px;
}

.payment-information-text {
  font-family: "Montserrat";
  font-size: 10px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.9;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-right: 10px;
}

.time {
  margin-top: 4px;
  font-family: "Montserrat";
  font-size: 9px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.transaction-history {
  font-family: "Montserrat";
  font-size: 10px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 2.1;
  letter-spacing: normal;
  text-align: right;
  color: #1e375a;
  text-decoration: underline;
}

.payment-information-container-history .time {
  display: flex;
  justify-content: flex-end;
}

.payment-information-amount_state {
  margin-right: 70px;
}

.payment-information-amount-container {
  margin-bottom: 22px;
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.payment-information-amount-container_state {
  margin-bottom: 10px;
}

.qr-code {
  width: 100px;
  height: 100px;
  object-fit: contain;
  margin-right: 22px;
}

.payment-information-amount-sum {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 300;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: normal;
  text-align: center;
  color: #1e375a;
  margin-right: 25px;
  margin-left: 45px;
}

.payment-information-amount-sum_state {
  margin-left: 0;
  margin-right: 10px;
}

.payment-information-text-sum {
  font-family: "Montserrat";
  font-size: 10px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.9;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.currency-type {
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.67;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  padding-top: 5px;
  margin-left: 20px;
  padding-left: 20px;
  border-left: 2px solid #e9ecf1;
  height: 30px;
}

.payment-information-input {
  width: 316px;
  height: 40px;
  padding: 11px 25px;
  border-radius: 10px;
  border: solid 1px #e8ecf3;
  background: url("../assets/images/copy.png") no-repeat 275px 10px;
  background-color: #ffffff;
  margin-top: 10px;
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 300;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.payment-information-input:focus {
  outline: 0;
  outline-offset: 0;
  border: solid 1px #8d75f8;
}

.payment-status {
  display: flex;
  justify-content: flex-start;
  margin-top: 25px;
}

.payment-status_state {
  margin-top: 15px;
}

.payment-status-text {
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: normal;
  text-align: left;
  color: #44a7e1;
  margin-right: 10px;
}

.payment-information-alert {
  display: flex;
  flex-direction: row;
}

.alert-icon {
  width: 18px;
  height: 18px;
  margin-right: 12px;
}

.alert-text {
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 300;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #919aa7;
}

.pay-button-submit {
  width: 223px;
  height: 40px;
  border-radius: 10px;
  border: solid 1px #8d75f8;
  background-color: rgba(0, 0, 0, 0);
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.36;
  letter-spacing: normal;
  text-align: center;
  color: #8d75f8;
}

.pay-button-submit:hover {
  background: rgb(140, 116, 247);
  background: linear-gradient(
    90deg,
    rgba(140, 116, 247, 1) 23%,
    rgba(140, 116, 247, 0.9332107843137255) 48%,
    rgba(186, 175, 235, 0.865983893557423) 79%
  );
  color: #ffffff;
  transition: 0.3s ease-in-out;
}

.pay-button-submit_state {
  border-radius: 10px;
  border: solid 1px #e8ecf3;
  background-color: rgba(0, 0, 0, 0);
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.36;
  letter-spacing: normal;
  text-align: center;
  color: #e8ecf3;
}
</style>