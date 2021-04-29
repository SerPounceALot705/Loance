<template>
  <div class="page">
    <Header />
    <section class="transaction-history">
      <h3 class="transaction-history-title">История транзакций</h3>
      <input class="transaction-history-input" placeholder="Поиск по номеру" />

      <div class="transaction-history-dropdown-container">
        <select class="transaction-history-select">
          <option selected>Кредитный модуль</option>
        </select>
        <select class="transaction-history-select">
          <option selected>Все типы операций</option>
        </select>
        <select class="transaction-history-select">
          <option selected>Все активы</option>
        </select>
        <select class="transaction-history-select">
          <option selected>Все статусы</option>
        </select>
      </div>
      <div class="transaction-history-filters">
        <span>Дата/Время</span>
        <span>Номер</span>
        <span>Тип операции</span>
        <span>Актив</span>
        <span
          >Сумма(с вычетом комиссии)</span
        >
        <span>Статус</span>
      </div>
      <div class="transaction-history-item">
        <div class="transaction-history-details-button">
          <img src="../assets/images/arrow1.png" alt="arrow" />
        </div>
        <div class="transaction-date-time-container">
          <span class="transaction-history-date">
            08.07.2019
            <p class="transaction-history-time">13:00</p>
          </span>
        </div>
        <span class="transaction-history-number">#210445</span>
        <span class="transaction-history-type">Пополнение</span>
        <div class="transaction-history-assets-container">
          <img src="../assets/images/btc.png" />
          <span class="transaction-history-assets-text">Bitcoin</span>
        </div>
        <span class="transaction-history-total">1.000023445 BTC</span>

        <span class="transaction-history-status transaction-history-status_paid"
          >Оплачено,
          <p>подтверждается</p></span
        >
        <div class="transaction-history-settings">
          <img src="../assets/images/3d.png" alt="settings" />
        </div>
      </div>
      <div class="transaction-history-more-details-container">
        <span class="transaction-history-more-details-transaction"
          >Транзакций в сети:
          <p class="carried-out">Проведено 3/10</p></span
        >
        <span class="transaction-history-more-details-hash"
          >Отследить по HASH:
          <p class="tracking">Отследить</p></span
        >
        <span class="transaction-history-more-details-time-title"
          >Осталось времени на операцию:
          <p class="transaction-history-more-details-time">
            0 мин : 59 мин
          </p></span
        >
      </div>
      <div class="transaction-history-item">
        <div class="transaction-history-details-button">
          <img src="../assets/images/arrow1.png" alt="arrow" />
        </div>
        <div class="transaction-date-time-container">
          <span class="transaction-history-date">
            08.07.2019
            <p class="transaction-history-time">13:00</p>
          </span>
        </div>
        <span class="transaction-history-number">#210445</span>
        <span class="transaction-history-type"
          >Увеличение
          <p>кредит.лимита</p></span
        >
        <div
          class="transaction-history-assets-container"
        >
          <img src="../assets/images/btc.png" />
          <span class="transaction-history-assets-text">Bitcoin</span>
        </div>
        <span class="transaction-history-total">1.000023445 BTC</span>

        <span
          class="transaction-history-status transaction-history-status_waiting"
          >Ожидание оплаты</span
        >
        <div
          class="transaction-history-settings"
        >
          <img src="../assets/images/3d.png" alt="settings" />
        </div>
      </div>
      <div class="transaction-history-item">
        <div class="transaction-history-details-button">
          <img src="../assets/images/arrow1.png" alt="arrow" />
        </div>
        <div class="transaction-date-time-container">
          <span class="transaction-history-date">
            08.07.2019
            <p class="transaction-history-time">13:00</p>
          </span>
        </div>
        <span class="transaction-history-number">#210445</span>
        <span class="transaction-history-type">Вывод средств</span>
        <div
          class="transaction-history-assets-container"
        >
          <img src="../assets/images/btc.png" />
          <span class="transaction-history-assets-text">Bitcoin</span>
        </div>
        <span class="transaction-history-total">1.000023445 BTC</span>

        <span
          class="transaction-history-status transaction-history-status_canceled"
          >Отменено</span
        >
        <div
          class="transaction-history-settings transaction-history-settings_canceled"
        >
          <img src="../assets/images/3d.png" alt="settings" />
        </div>
      </div>
      <div class="transaction-history-item">
        <div class="transaction-history-details-button">
          <img src="../assets/images/arrow1.png" alt="arrow" />
        </div>
        <div class="transaction-date-time-container">
          <span class="transaction-history-date">
            08.07.2019
            <p class="transaction-history-time">13:00</p>
          </span>
        </div>
        <span class="transaction-history-number">#210445</span>
        <span class="transaction-history-type">Погашение займа</span>
        <div
          class="transaction-history-assets-container"
        >
          <img src="../assets/images/payeer.png" />
          <span class="transaction-history-assets-text">Payeer</span>
        </div>
        <span
          class="transaction-history-total"
          >1.000023445 BTC</span
        >

        <span
          class="transaction-history-status transaction-history-status_confirmed"
          >Подтверждено</span
        >
        <div
          class="transaction-history-settings"
        >
          <img src="../assets/images/3d.png" alt="settings" />
        </div>
      </div>
      <div class="transaction-history-item">
        <div class="transaction-history-details-button">
          <img src="../assets/images/arrow1.png" alt="arrow" />
        </div>
        <div class="transaction-date-time-container">
          <span class="transaction-history-date">
            08.07.2019
            <p class="transaction-history-time">13:00</p>
          </span>
        </div>
        <span class="transaction-history-number">#210445</span>
        <span class="transaction-history-type">Увеличение залога</span>
        <div
          class="transaction-history-assets-container"
        >
          <img src="../assets/images/payeer.png" />
          <span class="transaction-history-assets-text">Payeer</span>
        </div>
        <span
          class="transaction-history-total"
          >1.000023445 BTC</span
        >

        <span
          class="transaction-history-status transaction-history-status_paid-status"
          >Оплачено</span
        >
        <div
          class="transaction-history-settings"
        >
          <img src="../assets/images/3d.png" alt="settings" />
        </div>
      </div>
      <div class="transaction-history-item">
        <div class="transaction-history-details-button">
          <img src="../assets/images/arrow1.png" alt="arrow" />
        </div>
        <div class="transaction-date-time-container">
          <span class="transaction-history-date">
            08.07.2019
            <p class="transaction-history-time">13:00</p>
          </span>
        </div>
        <span class="transaction-history-number">#210445</span>
        <span class="transaction-history-type"
          >Суточная оплата
          <p>за % по кредиту</p></span
        >
        <div
          class="transaction-history-assets-container transaction-history-assets-container_daily-payment"
        >
          <img src="../assets/images/payeer.png" />
          <span class="transaction-history-assets-text">Payeer</span>
        </div>
        <span
          class="transaction-history-total transaction-history-total_daily-payment"
          >1.000023445 BTC</span
        >

        <span
          class="transaction-history-status transaction-history-status_daily-payment"
          >Оплачено</span
        >
        <div
          class="transaction-history-settings transaction-history-settings_daily-payment"
        >
          <img src="../assets/images/3d.png" alt="settings" />
        </div>
      </div>
    </section>
  </div>
</template>


<script>
import Header from "../components/Header.vue";
export default {};
</script>

<style>
.page {
  width: 100%;
  height: 1080px;
  max-width: 100%;
  background-image: url("../assets/images/Web 1920 – 1.png");
}

.transaction-history {
  width: 1110px;
  margin: 0 auto;
  height: 871px;
  padding: 36px;
  border-radius: 15px;
  background-color: #ffffff;
}

.transaction-history-title {
  font-family: "Montserrat";
  font-size: 22px;
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.14;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-bottom: 30px;
}

.transaction-history-input {
  width: 100%;
  height: 33px;
  border-radius: 10px;
  padding: 5px 10px 5px 40px;
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
  margin-bottom: 20px;
  appearance: none;
}

.transaction-history-input:focus {
  outline: 0;
  outline-offset: 0;
  border: solid 1px #8d75f8;
}


.transaction-history-dropdown-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.transaction-history-select {
  width: 240px;
  height: 50px;
  padding: 10px;
  border-radius: 4px;
  border: solid 1px #e8ecf3;
  background-color: #ffffff;
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.67;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  background: url("../assets/images/arrow3.png") no-repeat 210px 22px;
  margin-bottom: 41px;
}

.transaction-history-select:focus {
  outline: 0;
  outline-offset: 0;
  border: solid 1px #8d75f8;
}

.transaction-history-filters {
  width: 1044px;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  padding: 12px;
  margin-bottom: 8px;
  border: 1px solid #ffffff;
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: center;
  color: #acb1b7;
}

.transaction-history-filters span:nth-child(1) {
   width: 90px;
   text-align: left;
}

.transaction-history-filters span:nth-child(2) {
  width: 60px;
  text-align: left;
}

.transaction-history-filters span:nth-child(3) {
  width: 146px;
  text-align: left;
}

.transaction-history-filters span:nth-child(4) {
  width: 95px;
  text-align: left;
}

.transaction-history-filters span:nth-child(5) {
  width: 134px;
  text-align: left;
}

.transaction-history-filters span:nth-child(6) {
  width: 150px;
  text-align: left;
}

.transaction-date-time-container {
  width: 90px;
  display: flex;
  align-items: flex-start;
}

.transaction-history-number {
  width: 60px;
}

.transaction-history-type {
  width: 146px;
}

.transaction-history-assets-container {
  width: 95px;
}

.transaction-history-total {
  width: 134px;
}

.transaction-history-status {
    width: 150px;
}

.transaction-history-settings {
}


.transaction-history-item {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  width: 1044px;
  height: 60px;
  padding: 12px;
  border-radius: 5px;
  box-shadow: 0 0 5px 0 rgba(0, 0, 0, 0.06);
  border: solid 1px #e8ecf3;
  background-color: #ffffff;
  position: relative;
  text-align: center;
  align-items: center;
  margin-bottom: 10px;
}

.transaction-history-details-button {
  position: absolute;
  top: 30%;
  left: 22px;
}

.transaction-history-date {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.29;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.transaction-history-time {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #919aa7;
}

.transaction-history-number {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #919aa7;
}

.transaction-history-type {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.29;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.transaction-history-assets-container {
  display: flex;
  flex-direction: row;
  align-items: center;
}

.transaction-history-assets-container img {
  margin-right: 10px;
}

.transaction-history-assets-container_confirmed {
  width: 36px;
  height: 24px;
  margin-left: 50px;
}

.transaction-history-assets-text {
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

.transaction-history-total {
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

.transaction-history-settings {
  position: absolute;
  top: 32%;
  right: 30px;
}

.transaction-history-status_paid {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.29;
  letter-spacing: normal;
  text-align: left;
  color: #8d75f8;
}

.transaction-history-status_waiting {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.29;
  letter-spacing: normal;
  text-align: left;
  color: #75daf8;
}

.transaction-history-status_canceled {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.29;
  letter-spacing: normal;
  text-align: left;
  color: #8d75f8;
}

.transaction-history-status_confirmed {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.29;
  letter-spacing: normal;
  text-align: left;
  color: #e1dd6a;
}

.transaction-history-status_paid-status {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.29;
  letter-spacing: normal;
  text-align: left;
  color: #6ae181;
}

.transaction-history-status_daily-payment {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.29;
  letter-spacing: normal;
  text-align: left;
  color: #6ae181;
}

.transaction-history-more-details-container {
  display: flex;
  flex-direction: row;
  text-align: center;
  align-items: center;
  width: 1044px;
  height: 58px;
  padding: 10px;
  border-radius: 5px;
  border: solid 1px #e8ecf3;
  background-color: #fcfcfc;
  margin-bottom: 20px;
}

.transaction-history-more-details-transaction {
  display: flex;
  flex-direction: row;
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.46;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-left: 25px;
  text-align: center;
}

.carried-out {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: left;
  color: #70abff;
  margin-left: 10px;
  margin-right: 50px;
}

.transaction-history-more-details-hash {
  display: flex;
  flex-direction: row;
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.46;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.tracking {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: left;
  color: #acb1b7;
  text-decoration: underline;
  margin-left: 10px;
  margin-right: 50px;
}

.transaction-history-more-details-time-title {
  display: flex;
  flex-direction: row;
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.46;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.transaction-history-more-details-time {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-left: 10px;
}
</style>