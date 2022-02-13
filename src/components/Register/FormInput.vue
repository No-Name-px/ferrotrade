<template>
  <div
    :class="[stl == 'darkSide' ? 'form-input__theme_dark-side' : '']"
    class="form-input"
  >
    <div class="form-input__info" v-if="title || hasRedact">
      <template v-if="title"> {{ title }}: </template>
      <button @click="changeRedactable" v-if="hasRedact" class="btn btn-redact" type="button">
        Редактировать поле
      </button>
    </div>
    <textarea
      v-model="value"
      v-if="type == 'textarea'"
      class="form-input__input form-input__input__textarea"
      type="text"
      :disabled="!redactable"
      :placeholder="ph"
    />
    <div v-else-if="type == 'counter'" class="form-input__counter">
      <input
        v-model="value"
        type="number"
        class="form-input__input form-input__input__counter"
        :disabled="!redactable"
        :placeholder="ph"
      />
      <div class="form-input__buttons">
        <button @click="value--" class="form-input__button center" type="button">-</button>
        <button @click="value++" class="form-input__button center" type="button">+</button>
      </div>
    </div>
    <input
      v-model="value"
      v-else
      class="form-input__input"
      :disabled="!redactable"
      type="text"
      :placeholder="ph"
    />
  </div>
</template>

<script>
export default {
  name: "FormInput",
  data() {
    return {
      value: "",
      redactable: true,
    };
  },
  methods: {
    changeRedactable() {
      this.redactable = !this.redactable;
    },
  },
  props: {
    title: String,
    type: String,
    hasRedact: Boolean,
    stl: String,
    ph: String,
  },
};
</script>

<style scoped>
.form-input {
  display: flex;
  flex-direction: column;
}
.form-input__info {
  display: flex;
  align-items: center;
  margin-bottom: 0.6rem;
}
.form-input__input:disabled {
  background-color: var(--color-side);
}
.btn-redact {
  margin-left: 0.2rem;
}
.form-input__counter {
  display: flex;
  justify-content: space-between;
}
.form-input__input__counter {
  margin: 0;
  width: 60%;
}
.form-input__buttons {
  display: flex;
  width: 35%;
  height: 100%;
}
.form-input__button {
  width: 45%;
  border-radius: 0.5rem;
  font-size: 1.5rem;
  height: 100%;
}
.form-input__button:nth-child(2) {
  margin-left: 0.4rem;
}
.form-input__input__textarea {
  resize: vertical;
}
.form-input__theme_dark-side .form-input__input {
  display: flex;
  border: 0.2rem solid var(--color-side-dark);
}
</style>