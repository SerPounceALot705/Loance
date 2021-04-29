<template>
    <section class="header">
        <div class="header-logo-container">
            <img class="header-logo" alt="logo" src="../assets/images/logo.png">
            <img class="header-name" alt="logo-name" src="../assets/images/loance.png">
        </div>
        <ul class="header-menu">
            <li>
                <a href="" class="header-link">
                        <img class="header-menu-img_accounting" alt="accounting" src="../assets/images/001-accounting.png">
                        <span class="header-menu-text">Займ</span>   
                    </a>
            </li>
            <li>
                <a href="" class="header-link">
                        <img class="header-menu-img" alt="investments" src="../assets/images/001-return.png">
                        <span class="header-menu-text">Инвестиции</span>
                    </a>  
            </li>
        </ul>
        <ul class="header-transaction">
            <li>
                 <a href="" class="header-link header-link-transaction">
                    <img class="header-menu-img" alt="transaction" src="../assets/images/002-transaction.png">
                    <span class="header-menu-text">Транзакции</span>   
                </a>
            </li>
        </ul>
        <!-- <div class="header-menu">
            <div class="header-menu-container">
                <div class="menu-item-container">
                    <a href="" class="header-link">
                        <img class="header-menu-img_accounting" alt="accounting" src="../images/001-accounting.png">
                        <p class="header-menu-text">Займ</p>   
                    </a>
                    <div class="actived-link"></div>  
                </div>
                <div class="menu-item-container">
                    <a href="" class="header-link">
                        <img class="header-menu-img" alt="investments" src="../images/001-return.png">
                        <p class="header-menu-text">Инвестиции</p>
                    </a>
                    
                </div>
                <div class="inactived-link"></div>
            </div>
             
            <div class="header-container-transaction">
                <a href="" class="header-link header-link-transaction">
                    <img class="header-menu-img" alt="transaction" src="../images/002-transaction.png">
                    <p class="header-menu-text">Транзакции</p>   
                </a>
                <div class="inactived-link"></div> 
            </div>
        </div>-->
        
    <div class="header-notifications-container">
        <a href=""><img class="notifications" alt="notifications" src="../assets/images/notifications.png"></a>
        <a href=""><img class="alerts" alt="alerts" src="../assets/images/alerts.png"></a>
    </div>
    <v-select
    v-model="selected"
        :options="options"
        :clearable="false"
        :searchable="false"
        :placeholder="'placeholder'"
        label="title"
        class="account"
    >
    <template #selected-option="{ iconUrl}">
        <img :src="iconUrl" alt="icon-account" class="icon-account" />
    </template>
    </v-select>
    </section>
</template>


<style>

@font-face {
    font-family: "Montserrat-Black";
    src: url("../vendor/fonts/Montserrat-Black.ttf") format("ttf");;
}

@font-face {
    font-family: "Montserrat-BlackItalic";
    src: url("../vendor/fonts/Montserrat-BlackItalic.ttf") format("ttf");;
}

@font-face {
    font-family: "Montserrat-Bold";
    src: url("../vendor/fonts/Montserrat-Bold.ttf") format("ttf");;
}

@font-face {
    font-family: "Montserrat-BoldItalic";
    src: url("../vendor/fonts/Montserrat-BoldItalic.ttf") format("ttf");;
}

.page {
    width: 100%;
}

.header {
    width: 70%;
    height: 74px;
    margin: 0 auto;
    border-radius: 15px;
    background-color:#ffffff;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.header-logo-container {
    display: flex;
    justify-content: space-between;
    margin-right: 360px;
}

.header-logo {
    width: 28px;
    height: 31px;
    margin-right: 20px;
    object-fit: contain;
}

.header-name {
    width: 88px;
    height: 20px;
    margin-top: 5px;
    object-fit: contain;
}

ul.header-menu {
    list-style: none;
    padding: 0;
    display: flex;
    justify-content: space-between;
    margin-right: 53px;
}

ul.header-transaction {
    list-style: none;
    padding: 0;
    display: flex; 
}

.header-link {
    display: flex;
    flex-direction: row;
    text-decoration: none;
    margin-right: 24px;   
}

/*.actived-link {
    height:4px;
    background-color: #8d75f8;
    border-radius: 5px;
    margin-top: 5px;
    box-shadow: 1px 1px 3px 0 rgba(0, 0, 0, 0.16);
}

.inactived-link {
    height: 4px;
    margin-top: 5px;
    border-radius: 5px;
    background-color: #e9ecf1;
}*/

.header-menu-img {
    width: 26px;
    height: 26px;
    margin: 0 11px 0 0;
    object-fit: contain;
}

.header-menu-img_accounting{
    width: 25px;
    height: 25px;
    margin: 0 11px 0 0;
    object-fit: contain;
}

.header-menu-text {
    height: 15px;
    margin: 5px 0;
    font-family: "Montserrat";
    font-size: 12px;
    font-weight: 600;
    font-stretch: normal;
    font-style: normal;
    letter-spacing: normal;
    text-align: left;
    color: #1e375a;
    text-decoration: none;
}

.header-notifications-container {
    margin-left: 53px;
    margin-right: 22px;
}

.notifications {
  margin-right: 20px;  
}

.account {
    width: 63px;
    height: 26px;
    border-radius: 13px;
    box-shadow: 0 1px 2px 0 rgba(30, 55, 90, 0.16);
    background-color: #ffffff;
    padding: 0;
    margin-bottom: 5px;
    margin-right: 21px;
}

.icon-account {
    width: 26px;
    height: 26px;
    margin-right: 5px;
    object-fit: contain;
}

.account .vs__dropdown-toggle {
    border: none;
}

.account .vs__selected {
    margin: 0;
    padding: 0;
}

.account .vs__selected-options {
    width: 63px;
    height: 26px;
    margin: 0;
    padding: 0;   
}

    
</style>


<script>


export default {
    data() {
        return {
            options: [
                {
                id: "1",
                iconUrl: require("~/assets/images/account-button.png"),
                },
            ],
            selected: {
                id: "1",
            iconUrl: require("~/assets/images/account-button.png"),
            },
        }
    }
}
</script>