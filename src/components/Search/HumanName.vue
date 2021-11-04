<template>
  <div class="main-container">
    <div class="component-name">
      <h2>Nom humain</h2>
    </div>

    <b-container class="gender-container">
      <b-row align-h="around">
        <b-button class="gender-button" variant="light" @click="selectMaleGender">Masculin</b-button>
        <b-button class="gender-button" variant="light" @click="selectFemaleGender">Féminin</b-button>
      </b-row>
    </b-container>

    <b-container class="origin-container">
      <b-row align-h="around">
        <b-form-select class="origin-select" v-model="selected" :options="options" @change="selectNameOrigin"></b-form-select>
      </b-row>
    </b-container>

    <div class="copy-container">
      <b-button type="submit" variant="light">Générer</b-button>
    </div>

    <b-container class="result-container">
      <b-card class="mt-3" header="Résultat">
        <pre class="m-0" id="name-result"></pre>
      </b-card>
    </b-container>
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
      ],
      gender: null,
      origin: null
    }
  },
  methods: {
    selectFemaleGender: function() {
      this.gender = 'f'
      console.log(this.gender)
    },
    selectMaleGender: function() {
      this.gender = 'm'
      console.log(this.gender)
    },
    selectNameOrigin: function() {
      this.origin = this.selected
      console.log(this.origin);
      this.displayGeneratedName()
    },
    displayGeneratedName: function() {
      document
        .getElementById("name-result")
        .innerText = 'Sexe : ' + this.gender + ' Origine : ' + this.origin
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