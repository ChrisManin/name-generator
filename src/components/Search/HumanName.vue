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

    <b-container class="search-container">
      <b-row align-h="around">
        <b-input-group class="firstname-search">
          <template #prepend>
            <b-button variant="light">Prénom</b-button>
          </template>
          <b-form-input></b-form-input>
        </b-input-group>

        <b-input-group class="lastname-search">
          <template #prepend>
            <b-button variant="light">Nom</b-button>
          </template>
          <b-form-input></b-form-input>
        </b-input-group>
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
};
</script>

<style lang="scss" scoped>
@import "../../assets/styles/components/search/global-search.scss";
</style>