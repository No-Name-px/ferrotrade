<template>
  <div class="searching page-content">
    <div class="searching__searching-bar">
      <FormInput
        ph="Введите/отсканируйте информацию"
        class="searching__input"
        type="text"
      />
      <button class="btn searching__btn">Найти</button>
    </div>
  </div>
</template>

<script>
import FormInput from "../../components/Register/FormInput.vue";

export default {
  name: "searching",
  components: {
    FormInput,
  },
};
</script>

<style scoped>
.searching {
  padding-left: 3rem;
}
.searching__searching-bar {
  width: 100%;
  display: flex;
}
.searching__input {
  width: 60%;
}
.searching__btn {
  margin-left: 2rem;
}
</style>
