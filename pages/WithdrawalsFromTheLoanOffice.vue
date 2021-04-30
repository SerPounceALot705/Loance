<template>
  <div class="page">
    <Header />
    <section class="withdrawals-from-the-loan-office">
      <h3 class="withdrawals-from-the-loan-office-title">
        Вывод средств из кабинета займа
      </h3>
      <div class="withdrawals-from-the-loan-office-content-container">
        <div>
          <div class="withdrawals-from-the-loan-office-container">
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
                    <span class="calc-value">1400.00</span>
                    <img
                      class="transfer"
                      alt="arrows"
                      src="../assets/images/transfer.png"
                    />
                    <span class="calc-value">1.000000000</span>
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
            <button class="withdrawals-button">
              Вывести средства на кошелек
            </button>
          </div>
          <div class="transfer-request">
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
                    src="../assets/images/btc.png"
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
                  src="../assets/images/okbig.png"
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
                    src="../assets/images/btc.png"
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
                    src="../assets/images/btc.png"
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

.withdrawals-from-the-loan-office {
  width: 70%;
  margin: 0 auto;
}

.withdrawals-from-the-loan-office-content-container {
  display: flex;
  flex-direction: row;
}

.withdrawals-from-the-loan-office-container {
  width: 445px;
  height: 730px;
  padding: 36px;
  border-radius: 15px;
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  margin-right: 30px;
}

.withdrawals-from-the-loan-office-title {
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
  margin-top: 27px;
}

span.withdrawals-from-the-loan-office-subtitle {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.31;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  display: block;
  width: 226px;
  margin-bottom: 13px;
}

.withdrawals-from-the-loan-office-input {
  width: 382px;
  height: 60px;
  padding: 12px;
  border-radius: 10px;
  border: solid 1px #e8ecf3;
  background-color: #ffffff;
  margin-bottom: 32px;
}

.replenishment-sum-title_withdrawals-state {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.replenishment-methods_withdrawals-state {
  margin-bottom: 32px;
}

.withdrawals-from-the-loan-office-button {
  width: 381px;
  height: 33px;
  border-radius: 10px;
  border: solid 1px #8d75f8;
  background-color: #ffffff;
  font-family: "Montserrat";
  font-size: 10px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.9;
  letter-spacing: normal;
  text-align: center;
  color: #8d75f8;
  cursor: pointer;
}

.replenishment-calc_withdrawals-state {
  margin-bottom: 23px;
}

.withdrawals-from-the-loan-office-text-container {
  display: flex;
  flex-direction: column;
  margin-top: 40px;
}

.withdrawals-from-the-loan-office-text-title {
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.67;
  letter-spacing: normal;
  text-align: left;
  color: #acb1b7;
  display: block;
  margin-bottom: 7px;
}

.withdrawals-from-the-loan-office-text {
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 300;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.67;
  letter-spacing: normal;
  text-align: left;
  color: #acb1b7;
}

.withdrawals-button {
  width: 381px;
  height: 60px;
  border-radius: 10px;
  background: rgb(103, 104, 244);
  background: linear-gradient(
    90deg,
    rgba(103, 104, 244, 1) 32%,
    rgba(179, 131, 253, 1) 70%
  );
  border: none;
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.19;
  letter-spacing: normal;
  text-align: center;
  color: #ffffff;
  margin-top: 40px;
  cursor: pointer;
}

.current-transactions-text {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.31;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  display: block;
  margin-bottom: 32px;
}

.current-transactions {
  width: 350px;
  height: 400px;
  padding: 36px 36px 32px;
  border-radius: 15px;
  background-color: #ffffff;
  border-bottom: 1px solid #e7e7e7;
}

.table-info-status_current-transactions-state {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #ca3886;
  padding: 0;
}

.withdrawals-from-the-loan-office-info {
  width: 350px;
  height: 330px;
  padding: 36px 25px 30px;
  border-radius: 15px;
  background-color: #ffffff;
}

.name-of-line_withdrawals-status {
  padding: 0;
}

.name-of-line_withdrawals-from-the-loan-office-info {
  padding: 0;
}

.table-info-status_withdrawals-from-the-loan-office-info-state {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #38ca89;
  padding: 0;
}

.withdrawals-from-the-loan-office-info table {
  table-layout: auto;
  width: 300px;
}
</style>