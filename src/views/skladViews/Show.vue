<template>
  <div class="party-page page-content">
    <div class="party-page__items">
      <div class="party-page__representation">
        <div class="party-page__all-sort">
          Сортировать по:
          <CastomSelector
            class="party-page__all-sort-selector"
            :options="sort"
            :selected="selectedSort"
            @select-change="optionSelect"
          />
        </div>
        <div class="party-page__view">
          Карточки
          <CastomSwitcher
            class="party-page__view-switcher"
            v-model="isTableView"
          />
          Таблица
        </div>
      </div>
      <div class="party-page__cards">
        <CardItem />
        <CardItem />
        <CardItem />
        <CardItem />
        <CardItem />
        <CardItem />
      </div>
    </div>
    <CastomFilter class="party-page__filters" />
  </div>
</template>

<script>
import CardItem from "../../components/CardItem.vue";
import CastomSelector from "../../components/Show/CastomSelector.vue";
import CastomSwitcher from "../../components/Show/CastomSwitcher.vue";
import CastomFilter from "../../components/Show/CastomFilter.vue";

export default {
  name: "Show",
  components: {
    CardItem,
    CastomSelector,
    CastomSwitcher,
    CastomFilter,
  },
  data() {
    return {
      sort: [
        { name: "марке", value: "mark" },
        { name: "диаметру", value: "diametr" },
      ],
      selectedSort: "марке",
      isTableView: false,
    };
  },
  methods: {
    optionSelect(option) {
      this.selectedSort = option.name;
    },
  },
};
</script>

<style scoped>
.party-page {
  padding: 0 3rem;
  display: flex;
  justify-content: space-between;
}
.party-page__items {
  width: 80%;
  position: relative;
}
.party-page__representation {
  position: absolute;
  height: 50px;
  width: 75%;
  top: -50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-left: 1.5rem;
}
.party-page__all-sort {
  width: auto;
  display: flex;
  align-items: center;
}
.party-page__all-sort-selector {
  margin-left: 1rem;
}
.party-page__view {
  display: flex;
  align-items: center;
}
.party-page__view-switcher {
  margin: 0 1rem;
}
.party-page__cards {
  display: grid;
  grid-template-columns: 32% 32% 32%;
  column-gap: 2%;
  row-gap: 2%;
}
.party-page__filters {
  width: 18%;
}
</style>
