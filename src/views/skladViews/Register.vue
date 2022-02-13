<template>
  <form action="#" class="register-form page-content">
    <FormInput
      title="Марка"
      type="input"
      :hasRedact="true"
      stl="darkSide"
      class="register-form__input input__small"
    />
    <FormInput
      title="Диаметр"
      type="input"
      :hasRedact="true"
      stl="darkSide"
      class="register-form__input input__small"
    />
    <FormInput
      title="Упаковка"
      type="input"
      :hasRedact="true"
      stl="darkSide"
      class="register-form__input input__small"
    />
    <FormInput
      title="Плавка"
      type="input"
      :hasRedact="true"
      stl="darkSide"
      class="register-form__input input__small"
    />
    <FormInput
      title="Партия"
      type="input"
      :hasRedact="true"
      stl="darkSide"
      class="register-form__input input__small"
    />
    <FormInput
      title="Вес"
      type="input"
      :hasRedact="true"
      stl="darkSide"
      class="register-form__input input__small"
    />
    <FormInput
      title="Производитель"
      type="input"
      :hasRedact="true"
      stl="darkSide"
      class="register-form__input input__medium"
    />
    <FormInput
      title="Количество"
      type="counter"
      :hasRedact="false"
      stl="darkSide"
      class="register-form__input input__small"
    />
    <FormInput
      title="Комментарий"
      type="textarea"
      :hasRedact="true"
      stl="darkSide"
      class="register-form__input input__large"
    />
  </form>
</template>

<script>
import FormInput from "../../components/Register/FormInput.vue";

export default {
  name: "register",
  components: {
    FormInput,
  },
};
</script>

<style scoped>
.register-form {
  width: 55%;
  margin-left: auto;
  margin-right: auto;

  border: 5px solid var(--color-primary);
  border-radius: 1.5rem;
  padding: 1.5rem;
  flex-wrap: wrap;
}
.register-form__input {
  margin-top: 0.8rem;
}
.input__small {
  width: 35%;
}
.input__small:nth-child(2n) {
  margin-left: 5%;
}
.input__small:nth-child(1),
.input__small:nth-child(2) {
  margin-top: 0;
}
.input__medium {
  width: 60%;
}
.input__large {
  width: 100%;
}
</style>
