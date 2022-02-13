<template>
  <div class="card-item">
    <p class="cart-item__title">Позиция</p>
    <p class="card-item__text">Марка: 0dsfsdfdf</p>
    <p class="card-item__text">Диаметр: 0</p>
    <p class="card-item__text">Упаковка: 0</p>
    <p class="card-item__text">Партия: 0</p>
    <p class="card-item__text">Плавка: 0</p>
    <p class="card-item__text">Вес: 0</p>
    <p class="card-item__text">Комментарий: 0</p>
    <p class="card-item__text">Статус: 0</p>
  </div>
</template>

<script>
export default {
  name: "CardItem",
};
</script>

<style scoped>
.card-item {
  border: var(--color-primary) 3px solid;
  border-radius: 1rem;
  padding: 1.2rem 1.2rem;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.cart-item__title {
  font-size: 1.3rem;
  margin: 0 auto;
  margin-bottom: 0.6rem;
}
.card-item__text {
  font-size: 1.1rem;
  padding-top: 0.4rem;
  text-align: start;
  word-break: break-all;
}
</style>