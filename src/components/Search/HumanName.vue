<template>
  <div class="main-container">
    <div class="component-name">
      <h2>Nom humain</h2>
    </div>

    <b-container class="gender-container">
      <b-row align-h="around">
        <b-button class="gender-button" variant="light">Masculin</b-button>
        <b-button class="gender-button" variant="light">Féminin</b-button>
      </b-row>
    </b-container>

    <b-container class="origin-container">
      <b-row align-h="around">
        <b-form-select class="origin-select" v-model="selected" :options="options"></b-form-select>
      </b-row>
    </b-container>

    <b-container class="result-container">
      <b-row align-h="center">
        <b-form-input placeholder='Résultat'></b-form-input>
      </b-row>
    </b-container>
    <div class="copy-container">
      <b-button variant="light">Copier</b-button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HumanName",
  data() {
    return {
      selected: null,
      options: [
        { value: null, text: 'Sélectionnez l\'origine du prénom souhaité' },
        { value: 'ger', text: 'Allemagne' },
        { value: 'chi', text: 'Chine' },
        { value: 'dan', text: 'Danemark' },
        { value: 'eng', text: 'Grande-Bretagne' },
        { value: 'ita', text: 'Italie' },
        { value: 'jap', text: 'Japon' },
        { value: 'nor', text: 'Norvège' },
        { value: 'por', text: 'Portugal' },
        { value: 'spa', text: 'Espagne' },
        { value: 'swe', text: 'Suède' },
        { value: 'tur', text: 'Turkish' },
      ]
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../../assets/styles/components/search/global-search.scss";

.main-container {
  background-color: #239696;
}
</style>