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
          <div class="list-of-currencies">
            <div class="currency currency_actived">
              <span class="abbreviation"
                >BTC
                <p class="type-of-currency">Bitcoin</p>
              </span>
            </div>
            <div class="currency">
              <span class="abbreviation"
                >ETH
                <p class="type-of-currency">Ether</p>
              </span>
            </div>
            <div class="currency">
              <span class="abbreviation"
                >USD
                <p class="type-of-currency">US Dollar</p>
              </span>
            </div>
            <div class="currency">
              <span class="abbreviation"
                >EUR
                <p class="type-of-currency">Euro</p>
              </span>
            </div>
            <div class="currency">
              <span class="abbreviation"
                >USDT
                <p class="type-of-currency">Tether Omni</p>
              </span>
            </div>
            <div class="currency">
              <span class="abbreviation"
                >GBP
                <p class="type-of-currency">Pounds Sterling</p>
              </span>
            </div>
          </div>
          <table class="about-currency">
            <tr>
              <td width="125px" class="about-currency-title">Кошелек</td>
              <td class="about-currency-title">Баланс</td>
              <td class="about-currency-title">
                Рыночная стоимость
                <a
                  ><img
                    src="../assets/images/information.png"
                    alt="information-icon"
                /></a>
              </td>
            </tr>
            <tr>
              <td class="about-currency-name">
                <img
                  src="../assets/images/elipse.png"
                  alt="currency-colour-icon"
                />
                <p class="about-currency-name-text">Bitcoin</p>
              </td>
              <td width="125px" class="about-currency-sum">BTC 1.000023445</td>
              <td width="150px" class="about-currency-price">&#36;1320.00</td>
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
            <button class="top-up-balance-button">Пополнить баланс</button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Header from "../components/Header.vue";
import TransferWithinTheSystem from "../pages/TransfersWithinTheSystem.vue";
export default {};
</script>

<style>
.page {
  width: 100%;
  height: auto;
  max-width: 100%;
  background-image: url("../assets/images/Web 1920 – 1.png") no-repeat 100% 100%;
}

.loan-repayment {
  width: 70%;
  margin: 0 auto;
}

.loan-repayment-content-container {
  display: flex;
  flex-direction: row;
}

.about-currency tr {
  margin-bottom: 14px;
}

.methods-of-repayment {
  width: 540px;
  height: auto;
  padding: 30px;
  background-color: #ffffff;
  border-radius: 15px;
  margin-right: 30px;
}

.about-currency-name {
  display: flex;
  flex-direction: row;
  align-items: center;
}

.loan-repayment-title {
  font-family: "Montserrat";
  font-size: 25px;
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-top: 27px;
  margin-bottom: 47px;
}

.methods-of-repayment {
  display: flex;
  flex-direction: column;
}

.methods-of-repayment-title {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.25;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  display: block;
  margin-bottom: 19px;
}

.methods-of-repayment-input {
  width: 480px;
  height: 33px;
  padding: 10px 10px 10px 40px;
  border-radius: 10px;
  border: solid 1px #e8ecf3;
  background-color: #ffffff;
  background: url("../assets/images/search.png") no-repeat 10px 10px;
  font-family: "Montserrat";
  font-size: 10px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.9;
  letter-spacing: normal;
  text-align: left;
  color: #acb1b7;
  margin-bottom: 30px;
}

.list-of-currencies {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-bottom: 24px;
}

.currency {
  width: 68px;
  height: 60px;
  padding: 10px 5px;
  border-radius: 4px;
  box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.16);
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.currency_actived {
  border: 1px solid #e88d8d;
}

.abbreviation {
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.67;
  letter-spacing: normal;
  text-align: center;
  color: #1e375a;
  display: block;
  margin-bottom: 2px;
  height: 15px;
}

.type-of-currency {
  font-family: "Montserrat";
  font-size: 7px;
  font-weight: 300;
  font-stretch: normal;
  font-style: normal;
  line-height: 2.86;
  letter-spacing: normal;
  text-align: center;
  color: #1e375a;
  height: 9px;
}

.about-currency-title {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #acb1b7;
  padding-bottom: 14px;
}

.about-currency-title a {
  cursor: pointer;
}

.about-currency-name-text {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-left: 10px;
}

.about-currency-sum {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.about-currency-price {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: center;
  color: #1e375a;
}

.repayment-amount {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  display: block;
  margin-bottom: 12px;
}

.repayment-amount-input {
  width: 476px;
  height: 60px;
  padding: 10px;
  border-radius: 10px;
  border: solid 1px #e8ecf3;
  background-color: #ffffff;
  margin-bottom: 12px;
}

.estimated-repayment-amount {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  display: block;
  margin-bottom: 12px;
}

.estimated-repayment-amount-input {
  width: 476px;
  height: 60px;
  padding: 10px;
  border-radius: 10px;
  border: solid 1px #e8ecf3;
  background-color: #ffffff;
  margin-bottom: 34px;
}

.repayment-button {
  width: 476px;
  height: 60px;
  border-radius: 10px;
  border: solid 1px #8d75f8;
  background-color: rgba(0, 0, 0, 0);
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.19;
  letter-spacing: normal;
  text-align: center;
  color: #8d75f8;
  margin-bottom: 35px;
  cursor: pointer;
}

.repayment-button:hover {
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

.estimated-count-title {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.31;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  padding-bottom: 21px;
}

.estimated-count-subtitle {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  width: 150px;
}

.after-maturity_title {
  padding-bottom: 21px;
  padding-top: 0;
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: left;
  color: #38ca89;
  text-align: center;
}

.after-maturity {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: center;
  color: #38ca89;
  text-align: center;
}

.earlier {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: left;
  color: #b3c5df;
  padding-bottom: 15px;
  padding-top: 15px;
  text-align: center;
}

.earlier_title {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: left;
  color: #b3c5df;
  padding-bottom: 21px;
  text-align: center;
}

.estimated-count-table td {
  border-bottom: 1px solid #e8ecf3;
}

.current-loan {
  display: flex;
  flex-direction: column;
  border-radius: 15px;
  background-color: #ffffff;
  width: 350px;
  height: 360px;
}

.current-loan-container {
  display: flex;
  flex-direction: column;
  padding: 32px;
  height: 180px;
  border-bottom: 1px solid #e7e7e7;
}

.top-up-balance_current-loan {
  margin-left: 0;
  height: 160px;
  padding: 32px;
}

.current-loan-title {
  font-family: "Montserrat";
  font-size: 22px;
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.14;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  display: block;
  margin-bottom: 25px;
}

.current-loan-sum {
  font-family: "Montserrat";
  font-size: 25px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.12;
  letter-spacing: normal;
  text-align: left;
  color: #b3c5df;
}
</style>