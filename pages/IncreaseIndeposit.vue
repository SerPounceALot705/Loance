<template>
  <div class="page">
    <Header />
    <section class="increase-in-deposit">
      <h3 class="increase-in-deposit-title">Увеличение залога</h3>
      <div class="increase-in-deposit-container">
        <div class="transfer-of-assets-container transfer-of-assets-container_state">
          <div>
            <div class="replenishment-methods replenishment-methods_state">
              <h3 class="methods-subtitle">Выберите актив под залог:</h3>
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
              <h3 class="replenishment-sum-title replenishment-sum-title_state">
                Введите сумму увеличения актива:
              </h3>
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
        </div>
        <table class="increase-in-deposit-table">
          <tr class="increase-in-deposit-table-line">
            <td class="increase-in-deposit-table-title">Оценочный подсчет</td>
            <td class="increase-in-deposit-table-increase">После увеличения</td>
            <td class="increase-in-deposit-table-current">Текущие</td>
          </tr>
          <tr>
            <td class="increase-in-deposit-table-subtitle">Залог</td>
            <td class="increase-in-deposit-table-increase-sum">&#36;1300.00</td>
            <td class="increase-in-deposit-table-current-sum">&#36;1200.00</td>
          </tr>
          <tr class="increase-in-deposit-table-line">
            <td class="increase-in-deposit-table-subtitle">Взятый кредит</td>
            <td class="increase-in-deposit-table-increase-sum">&#36;700.00</td>
            <td class="increase-in-deposit-table-current-sum">&#36;600.00</td>
          </tr>
          <tr class="increase-in-deposit-table-line">
            <td class="increase-in-deposit-table-subtitle">Доступный кредит</td>
            <td class="increase-in-deposit-table-increase-sum">&#36;700.00</td>
            <td class="increase-in-deposit-table-current-sum">&#36;600.00</td>
          </tr>
        </table>
        <button class="increase-in-deposit-button">Увеличить актив</button>
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
          <div class="transfer-img">
            <img
              class="transfer-cheсkmark"
              alt="transfer-cheсkmark"
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

.transfer-of-assets-container_state {
    padding: 0;
}

.increase-in-deposit {
  width: 70%;
  margin: 0 auto;
}

.increase-in-deposit-container {
  width: 540px;
  padding: 36px;
  border-radius: 15px;
  background-color: #ffffff;
}

.increase-in-deposit-title {
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

.replenishment-methods_state {
  margin-bottom: 30px;
}

.replenishment-sum-title_state {
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

.increase-in-deposit-table-title {
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 600;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.31;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  border-bottom: none;
  padding-right: 25px;
  padding-bottom: 15px;
}

.increase-in-deposit-table-increase {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: left;
  color: #38ca89;
  border-bottom: none;
  padding-right: 10px;
  padding-bottom: 15px;
}

.increase-in-deposit-table-current {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: left;
  color: #b3c5df;
  border-bottom: none;
  padding-bottom: 15px;
  padding-left: 14px;
}

.increase-in-deposit-table-subtitle {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: left;
  color: #1e375a;
  padding-top: 10px;
  padding-bottom: 5px;
}

.transfer-img {
  width: 60px;
  height: 60px;
  padding: 10px;
  background-color: #39ca89;
  border-radius: 50%;
  margin-right: 40px;
}

.increase-in-deposit-table-increase-sum {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: left;
  color: #38ca89;
  text-align: center;
}

.increase-in-deposit-table-current-sum {
  font-family: "Montserrat";
  font-size: 13px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.62;
  letter-spacing: normal;
  text-align: left;
  color: #b3c5df;
  padding-left: 15px;
}

.increase-in-deposit-table tr {
  border-bottom: 1px solid #e8ecf3;
}

.table {
  border-collapse: collapse;
}

.increase-in-deposit-button {
  width: 460px;
  height: 61px;
  border-radius: 10px;
  background: rgb(103, 104, 244);
  background: linear-gradient(
    90deg,
    rgba(103, 104, 244, 1) 32%,
    rgba(179, 131, 253, 1) 70%
  );
  border: none;
  cursor: pointer;
  font-family: "Montserrat";
  font-size: 16px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.19;
  letter-spacing: normal;
  text-align: center;
  color: #ffffff;
  margin-top: 50px;
  margin-bottom: 25px;
}
</style>



