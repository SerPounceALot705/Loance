<template>
  <div class="page">
    <Header />
    <section class="transfers-within-the-system">
      <h3 class="transfers-within-the-system-title">Перевод внутри системы</h3>
      <div class="transfers-within-the-system-content-container">
        <div class="transfers-within-the-system-container">
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
          <div>
            <div class="replenishment-methods">
              <h3 class="methods-subtitle">
                Выберите актив для перевода внутри системы:
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
          <button class="transfers-within-the-system-button">
            Перевести участнику
          </button>
        </div>
        <div class="top-up-balance">
          <span class="top-up-balance-text">Не хватает баланса?</span>
          <button class="top-up-balance-button">Пополнить баланс</button>
        </div>
      </div>
      <div class="verify-data">
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
                src="../assets/images/btc.png"
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
          <button class="verify-data-button-submit">Все верно, открыть</button>
          <button class="verify-data-button-reject">Отклонить</button>
        </div>
      </div>
      <div class="transfer-data">
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
                src="../assets/images/btc.png"
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
        <div class="transfer-of-assets-info-container transfer-of-assets-info-container_verify-data">
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

.transfers-within-the-system {
  width: 70%;
  margin: 0 auto;
}

.transfers-within-the-system-content-container {
  display: flex;
  flex-direction: row;
}

.transfers-within-the-system-title {
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
  margin-bottom: 37px;
}

.transfers-within-the-system-subtitle {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.31;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  margin-bottom: 40px;
}

.transfers-within-the-system-text {
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

.transfers-within-the-system-input-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 22px;
  margin-bottom: 27px;
}

.transfers-within-the-system-input {
  width: 380px;
  height: 50px;
  padding: 16px 20px;
  border-radius: 4px;
  border: solid 1px #e8ecf3;
  background: url("../assets/images/ckeckmark.png") no-repeat 340px 16px;
  background-color: #ffffff;
}

.transfers-within-the-system-input-text {
  font-family: "Montserrat";
  font-size: 11px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: normal;
  text-align: left;
  color: #39ca89;
  margin-top: 7px;
}

.transfers-within-the-system-container {
  width: 444px;
  height: 640px;
  padding: 36px 32px;
  border-radius: 15px;
  background-color: #ffffff;
}

.transfers-within-the-system-button {
  width: 380px;
  height: 61px;
  padding: 22px;
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
  cursor: pointer;
}

.transfers-within-the-system-button:hover {
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
.top-up-balance {
  width: 350px;
  height: 170px;
  padding: 31px;
  border-radius: 15px;
  background-color: #ffffff;
  margin-left: 30px;
}

.top-up-balance-text {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.56;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.top-up-balance-button {
  width: 286px;
  height: 60px;
  padding: 20px;
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
  margin-top: 24px;
  cursor: pointer;
}

.top-up-balance-button:hover {
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

.verify-data {
  width: 444px;
  height: 342px;
  padding: 36px;
  border-radius: 15px;
  background-color: #ffffff;
}

.verify-data table {
  margin-top: 34px;
}

.verify-data-text {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.31;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.verify-data-table-title {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #acb1b7;
  padding-bottom: 20px;
  padding-right: 80px;
}

.verify-data-table-value {
  font-family: "Montserrat";
  font-size: 14px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  padding-bottom: 20px;
  display: flex;
  flex-direction: row;
  align-items: center;
}

.verify-data-table-img {
  margin-right: 10px;
  width: 18px;
  height: 18px;
}

.verify-data-button-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-top: 27px;
}

.verify-data-button-submit {
  width: 172px;
  height: 46px;
  border-radius: 10px;
  background-color: #8d75f8;
  border: none;
  font-family: "Montserrat";
  font-size: 11px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.91;
  letter-spacing: normal;
  text-align: center;
  color: #ffffff;
  cursor: pointer;
}

.verify-data-button-reject {
  width: 172px;
  height: 46px;
  border-radius: 10px;
  border: solid 1px #8d75f8;
  background-color: #ffffff;
  font-family: "Montserrat";
  font-size: 11px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.91;
  letter-spacing: normal;
  text-align: center;
  color: #1e375a;
  cursor: pointer;
}

.transfer-data {
  width: 444px;
  height: 342px;
  padding: 36px;
  border-radius: 15px;
  background-color: #ffffff;
}

.transfer-data-text {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.31;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
}

.transfer-data table {
  margin-top: 34px;
}

.transfer-of-assets-info-container_verify-data {
    margin-top: 20px;
}
</style>