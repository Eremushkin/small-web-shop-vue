<template>
  <div class="container">
    <div class="row" v-for="(row, rowIndex) in rows" :key="rowIndex">
      <div class="item" v-for="(item, itemIndex) in row" :key="itemIndex">
        <!-- Ваш контент для каждого элемента сетки -->
        <div class="content">
          {{ item.name }} <!-- Предположим, что у вас есть свойство "name" в каждом объекте массива -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    dataArray: {
      type: Array,
      required: true,
    },
    columns: {
      type: Number,
      default: 3,
    },
  },
  computed: {
    rows() {
      // Разделение массива на ряды согласно количеству колонок
      return this.chunkArray(this.dataArray, this.columns);
    },
  },
  methods: {
    chunkArray(array, size) {
      // Функция для разделения массива на ряды
      const result = [];
      for (let i = 0; i < array.length; i += size) {
        result.push(array.slice(i, i + size));
      }
      return result;
    },
  },
};
</script>

<style scoped>
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}

.row {
  display: flex;
}

.item {
  width: 200px;
  height: 200px;
  background-color: red;
  margin: 10px;
}

.content {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  color: white;
  font-weight: bold;
}
</style>
