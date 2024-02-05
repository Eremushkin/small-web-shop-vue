<template>
  <div class="my-component">
    <!-- Черный хедер -->
    <header class="header">Заголовок</header>

    <!-- Белое тело -->
    <div class="body">
      <!--      <FullBoxComponent/>-->
      <!--      <p>Текст или содержимое вашего компонента...</p>-->
      <!--      <pre>{{telegramWebAppValue}}</pre>-->
      <!--      <button class="close-web-app-button" @click="handleButtonClick">Закрыть</button>-->
      <GenericProductList>
        <LocalIncrementProductCard/>
        <LocalIncrementProductCard/>
        <LocalIncrementProductCard/>
        <LocalIncrementProductCard/>
        <LocalIncrementProductCard/>
      </GenericProductList>
    </div>
  </div>
</template>

<script>
// import FullBoxComponent from "@/components/FullBoxComponent";
import LocalIncrementProductCard from '@/components/LocalIncrementProductCard.vue';
import GenericProductList from "@/components/GenericProductList";

export default {
  name: 'MyComponent',
  components: {
    // FullBoxComponent,
    GenericProductList,
    LocalIncrementProductCard
  },
  created() {
    // При монтировании компонента получаем значение из window.Telegram.WebApp
    this.telegramWebAppValue = window.Telegram && window.Telegram.WebApp.initDataUnsafe.query_id;
    // this.telegramWebAppValue = "Text tett tet tett etet ";
  },
};
</script>


<style scoped>
/* Стили для компонента */
.my-component {
  display: flex;
  flex-direction: column;
  height: 100vh; /* 100% высоты видимой области экрана */
}

.header {
  background-color: black;
  color: white;
  padding: 1em;
  text-align: center;
}

.body {
  flex: 1; /* Занимает оставшееся свободное пространство внутри компонента */
  /*width: 450px;*/
  background-color: var(--tg-theme-bg-color);
  padding: 1em;
}
</style>