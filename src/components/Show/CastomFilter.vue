<template>
  <div class="filter">
    <div class="filter__item">
      <p class="filter__title">Марка:</p>
      <CastomCheckbox
        v-for="mark in MARKS"
        :key="mark"
        :label="mark"
        :value="mark"
        v-model="selectedMarks"
      />
    </div>
    <div class="filter__item">
      <p class="filter__title">Диаметр:</p>
      <CastomMultiSlider
        :min="minDiametr"
        :max="maxDiametr"
        :value="selectedDiametrs"
        @change:selectedDiametrs="changeDiametrs"
      />
      <div class="filter__text">
        От <span class="filter__numbers">{{ selectedDiametrs[0] }}</span> до
        <span class="filter__numbers">{{ selectedDiametrs[1] }}</span>
      </div>
    </div>
    <div class="filter__item">
      <p class="filter__title">Упаковка:</p>
      <CastomCheckbox label="Моток" value="Моток" v-model="selectedBoxes" />
      <CastomCheckbox label="К200" value="К200" v-model="selectedBoxes" />
      <CastomCheckbox label="Д200" value="Д200" v-model="selectedBoxes" />
    </div>
    <button class="btn btn-filter">Отфильтровать</button>
    <button class="btn btn-filter" @click="clearFilters">
      Очистить фильтр
    </button>
  </div>
</template>

<script>
import CastomCheckbox from "../../components/Show/CastomCheckbox.vue";
import CastomMultiSlider from "../../components/Show/CastomMultiSlider.vue";
import { mapActions } from "vuex";
import { mapGetters } from "vuex";

export default {
  name: "CastomFilter",
  components: {
    CastomCheckbox,
    CastomMultiSlider,
  },
  data() {
    return {
      selectedMarks: [],
      selectedBoxes: [],
      minDiametr: 0,
      maxDiametr: 10,
      selectedDiametrs: [0, 10],
    };
  },
  computed: {
    ...mapGetters(["MARKS"]),
  },
  methods: {
    ...mapActions(["GET_MARKS_FROM_API"]),
    clearFilters() {
      this.selectedMarks = [];
      this.selectedBoxes = [];
    },
    changeDiametrs(value) {
      this.selectedDiametrs = value;
    },
  },
  mounted() {
    this.GET_MARKS_FROM_API();
  },
};
</script>

<style scoped>
.filter__item {
  margin-bottom: 0.8rem;
}
.filter__title {
  margin-left: 0.6rem;
  margin-bottom: 0.6rem;
}
.btn-filter {
  margin-bottom: 0.4rem;
}
.filter__text {
  margin-top: 0.2rem;
}
.filter__numbers {
  background-color: var(--color-side);
  padding: 0.1rem 0.2rem;
  border-radius: 5px;
}
</style>
