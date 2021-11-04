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
      <b-button type="submit" variant="light" @click="generateName">Générer</b-button>
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
        { value: 'fre', text: 'France' },
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
    },
    generateName: function() {
      const apiUrl = process.env.VUE_APP_API_BASE_URL
      const apiKey = process.env.VUE_APP_API_BTN_KEY
      const numberParam = process.env.VUE_APP_NBR_LIM
      fetch(apiUrl + 'usage=' + this.origin + '&gender=' + this.gender + numberParam + '&key=' + apiKey)
        .then(function(res) {
          if (res.ok) {
            return res.json();
          }
        })
        .then(function(value) {
          console.log(value)
          document
            .getElementById("name-result")
            .innerText = value.names[0]
        })
        .catch(function(err) {
          console.log('Une erreur est survenue : ' + err);
      })
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