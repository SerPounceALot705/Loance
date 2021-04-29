<template>
  <div class="page">
    <Header />
    <section class="transfer-of-assets">
      <h3 class="transfer-of-assets-title">
        Перевод активов в инвестиционный кабинет
      </h3>
      <div class="transfer-of-assets-container">
        <h3 class="transfer-of-assets-subtitle">Выберите актив для перевода</h3>
        <div>
          <div class="replenishment-methods">
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
                #selected-option="{ iconUrl, title, subtitle, amount, balance }"
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
            <h3 class="replenishment-sum-title">Введите сумму перевода</h3>
            <div class="replenishment-calc">
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
        <button class="transfer-of-assets-button">Перевести инвестиции</button>
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
              />
              <p>Bitcoin</p>
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
import Header from "../components/Header.vue";
import BalanceReplenishment from "../pages/BalanceReplenishment.vue";

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

.transfer-of-assets {
  width: 70%;
  margin: 0 auto;
}

.transfer-of-assets-title {
  font-family: "Montserrat";
  font-size: 25px;
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-top: 53px;
  margin-bottom: 37px;
}

.transfer-of-assets-subtitle {
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
}

.transfer-of-assets-container {
  width: 444px;
  padding: 36px;
  border-radius: 15px;
  background-color: #ffffff;
}

.transfer-of-assets-button {
  width: 380px;
  height: 61px;
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

.transfer-of-assets-button:hover {
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

.transfer-request {
  width: 444px;
  height: 552px;
  padding: 36px;
  border-radius: 15px;
  background-color: #ffffff;
}

.transfer-request-title {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.31;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-bottom: 27px;
}

.name-of-line {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #acb1b7;
  width: 145px;
  padding-bottom: 15px;
}

.name-of-line_status {
  padding-top: 25px;
  padding-bottom: 0;
}

.icon-img {
  margin-right: 10px;
}

.table-info-time {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  padding-bottom: 15px;
}

.table-info-number {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  padding-bottom: 15px;
}

.table-info-type {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #20385b;
  padding-bottom: 15px;
}

.table-info-currency {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  padding-bottom: 15px;
  display: flex;
  flex-direction: row;
  align-items: center;
}

.table-info-sum {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  padding-bottom: 15px;
}

.table-info-status {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #6ae181;
  padding-top: 25px;
}

.transfer-table-status {
  margin-bottom: 20px;
}

.additional-info {
  font-family: "Montserrat";
  font-size: 12px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.75;
  letter-spacing: normal;
  text-align: left;
  color: #acb1b7;
  text-decoration: underline;
  cursor: pointer;
}

.transfer-of-assets-info-container {
  display: flex;
  flex-direction: row;
  margin-top: 35px;
}

.transfer-of-assets-img {
  width: 60px;
  height: 60px;
  padding: 10px;
  background-color: #39ca89;
  border-radius: 50%;
  margin-right: 35px;
}

.transfer-of-assets-info-text-container {
  display: flex;
  flex-direction: column;
}

.transfer-of-assets-info-text {
  width: 288px;
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.46;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-bottom: 7px;
}

.transfer-of-assets-info-link {
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
  cursor: pointer;
}
</style>