<template>
  <div class="exchange-form">
    <div class="exchange-rate">
      <span>Курс: 1 USDT = 94.32 RUB</span>
    </div>

    <div class="input-group">
      <label for="currencyFrom">Отдаете Тинькофф (RUB)</label>
      <input type="number" id="currencyFrom" placeholder="Min 150 000 RUB">
    </div>

    <div class="input-group">
      <label for="currencyTo">Получаете Tether (USDT) ERC20</label>
      <input type="number" id="currencyTo" placeholder="Min 1 590.33 USDT">
    </div>

<!--    <button class="exchange-btn">Обменять</button>-->
  </div>
</template>

<script>
export default {
  data() {
    return {
      currencyFrom: 'USDT_BEP20',
      currencyTo: 'BUSD',
      amountFrom: null,
      amountTo: null,
    };
  },
  mounted() {
    this.setupMainButton();
  },
  methods: {
    setupMainButton() {
      // Проверяем, доступен ли объект Telegram WebApp
      if (window.Telegram.WebApp) {
        // Инициализируем MainButton
        window.Telegram.WebApp.MainButton.show();
        window.Telegram.WebApp.MainButton.onClick(() => {
          this.exchange();
        });

        // Настройка доступности кнопки
        this.updateMainButtonState();
      }
    },
    updateMainButtonState() {
      if (this.amountFrom) {
        window.Telegram.WebApp.MainButton.enable();
      } else {
        window.Telegram.WebApp.MainButton.disable();
      }
    },
    exchange() {
      // Логика обмена валют
      console.log("Exchange initiated");
    },
  },
  watch: {
    // Следим за изменениями amountFrom, чтобы обновлять состояние MainButton
    amountFrom() {
      this.updateMainButtonState();
    }
  }
};
</script>

<style scoped>
.exchange-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.exchange-rate {
  display: flex;
  justify-content: space-between;
  padding: 10px;
  border-radius: 18px; /* Скругление углов как на референсе */
  border: 1px solid #ccc; /* Граница для наглядности */
}

.timer {
  font-style: italic;
}

.input-group {
  display: flex;
  flex-direction: column;
}

label {
  font-size: 14px;
  color: #333;
}

input {
  padding: 15px;
  margin-top: 8px;
  font-size: 16px;
  border-radius: 18px; /* Скругление углов как на референсе */
  border: 1px solid #ccc;
}

.exchange-btn {
  padding: 15px;
  border-radius: 18px; /* Скругление углов как на референсе */
  border: none;
  color: white;
  background-color: #4CAF50; /* Зеленый фон кнопки */
  cursor: pointer;
  transition: background-color 0.3s;
}

.exchange-btn:hover {
  background-color: #45a049;
}
</style>
