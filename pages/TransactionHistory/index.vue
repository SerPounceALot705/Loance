<template>
  <div class="page">
    <Header selectLine="transaction"/>
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
        <span>Сумма(с вычетом комиссии)</span>
        <span>Статус</span>
      </div>
      <div class="transaction-history-item-container" v-for="item in items" :key="item.id">
        <div class="transaction-history-item">
          <div
            v-on:click="item.info.isOpen = !item.info.isOpen"
            class="transaction-history-details-button"
          >
            <img
              :src="require('~/assets/images/arrow1.png')"
              :class="{ 'img-up': item.info.isOpen }"
              alt="arrow"
            />
          </div>
          <div class="transaction-date-time-container">
            <span class="transaction-history-date">
              {{ item.date }}
              <p class="transaction-history-time">{{ item.time }}</p>
            </span>
          </div>
          <span class="transaction-history-number">#{{ item.id }}</span>
          <span class="transaction-history-type">{{ item.type }}</span>
          <div class="transaction-history-assets-container">
            <img :src="item.assetsIconUrl" />
            <span class="transaction-history-assets-text">{{
              item.assets
            }}</span>
          </div>
          <span class="transaction-history-total">{{ item.sum }} BTC</span>

          <span
            class="transaction-history-status"
            :class="getStatuColorClass(item.status)"
            >{{ item.status }}</span
          >
          <div class="transaction-history-settings">
            <img :src="require('~/assets/images/3d.png')" alt="settings" />
          </div>
        </div>

        <div
          v-if="item.info.isOpen"
          class="transaction-history-more-details-container"
        >
          <span class="transaction-history-more-details-transaction"
            >Транзакций в сети:
            <a href="#" class="carried-out">
              Проведено {{ item.info.transacrionCount }}/10
            </a></span
          >
          <span class="transaction-history-more-details-hash"
            >Отследить по HASH:
            <a href="#" class="tracking">Отследить</a></span
          >
          <span class="transaction-history-more-details-time-title"
            >Осталось времени на операцию:
            <p class="transaction-history-more-details-time">
              {{ item.info.timeOut }}
            </p></span
          >
        </div>
      </div>
    </section>
  </div>
</template>


<script>
import Header from "~/components/Header.vue";
export default {
  name: "TransactionHistory",
  components: { Header },
  data() {
    return {
      items: [
        {
          id: 210450,
          date: "08.07.2019",
          time: "13:00",
          type: "Пополнение",
          assets: "Bitcoin",
          assetsIconUrl: require("~/assets/images/btc.png"),
          sum: "1.000023445 BTC",
          status: "Оплачено, подтверждается",
          info: {
            isOpen: false,
            transacrionCount: 3,
            hash: "testhash",
            timeOut: "0 мин : 59 мин",
          },
        },
        {
          id: 210449,
          date: "08.07.2019",
          time: "13:00",
          type: "Пополнение",
          assets: "Bitcoin",
          assetsIconUrl: require("~/assets/images/btc.png"),
          sum: "1.000023445 BTC",
          status: "Ожидание оплаты",
          info: {
            isOpen: false,
            transacrionCount: 3,
            hash: "testhash",
            timeOut: "0 мин : 59 мин",
          },
        },
        {
          id: 210448,
          date: "08.07.2019",
          time: "13:00",
          type: "Пополнение",
          assets: "Bitcoin",
          assetsIconUrl: require("~/assets/images/btc.png"),
          sum: "1.000023445 BTC",
          status: "Отменено",
          info: {
            isOpen: false,
            transacrionCount: 3,
            hash: "testhash",
            timeOut: "0 мин : 59 мин",
          },
        },
        {
          id: 210447,
          date: "08.07.2019",
          time: "13:00",
          type: "Пополнение",
          assets: "Bitcoin",
          assetsIconUrl: require("~/assets/images/payeer.png"),
          sum: "1.000023445 BTC",
          status: "Подтверждено",
          info: {
            isOpen: false,
            transacrionCount: 5,
            hash: "testhash",
            timeOut: "0 мин : 59 мин",
          },
        },
        {
          id: 210446,
          date: "08.07.2019",
          time: "13:00",
          type: "Пополнение",
          assets: "Payeer",
          assetsIconUrl: require("~/assets/images/payeer.png"),
          sum: "1.000023445 BTC",
          status: "Оплачено",
          info: {
            isOpen: false,
            transacrionCount: 10,
            hash: "testhash",
            timeOut: "0 мин : 59 мин",
          },
        },
        {
          id: 210445,
          date: "08.07.2019",
          time: "13:00",
          type: "Пополнение",
          assets: "Payeer",
          assetsIconUrl: require("~/assets/images/payeer.png"),
          sum: "1.000023445 BTC",
          status: "Оплачено",
          info: {
            isOpen: false,
            transacrionCount: 10,
            hash: "testhash",
            timeOut: "0 мин : 59 мин",
          },
        },
      ],
    };
  },
  methods: {
    getStatuColorClass: function (status) {
      switch (status) {
        case "Оплачено, подтверждается":
          return "transaction-history-status_paid";
        case "Ожидание оплаты":
          return "transaction-history-status_waiting";
        case "Отменено":
          return "transaction-history-status_canceled";
        case "Подтверждено":
          return "transaction-history-status_confirmed";
        case "Оплачено":
          return "transaction-history-status_paid-status";
      }
    },
  },
};
</script>

<style lang="scss">
@import "~assets/styles/_adaptive.scss";

.page {
  max-width: 1920px;
  margin: 0 auto;
  height: 1453px;
  background-image: url("~/assets/images/1470.png");
  background-repeat: no-repeat;

   @media #{$phone} {
    width: 100%;
    background-image: none;
    height: auto;

  }
}

</style>