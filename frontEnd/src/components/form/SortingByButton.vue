<template>
  <div class="form-group my-2 sortingByButton">
    <select
      class="form-select btn btn-secondary text-light p-1 sortingByButtonSelect"
      aria-label="Trier par"
      required
      v-model="valueSelected"
      @change="sendSelected"
    >
      <option disabled class="sortingByButtonSelectTextDisabled"
        >Trier par</option
      >
      <option value="recent">Plus récents</option>
      <option value="hotest">Plus brûlants</option>
      <option value="popular">Plus populaires</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "SortingByButton",
  data() {
    return {
      valueSelected: "recent",
    };
  },
  methods: {
    sendSelected() {
      this.$emit("select-value", this.valueSelected);
    },
  },
};
</script>

<style scoped lang="scss">
.sortingByButton {
  &Select {
    border-radius: 25px;
    &TextDisabled {
      color: white;
      background: rgba(0, 0, 0, 0.384);
    }
  }
}
</style>
