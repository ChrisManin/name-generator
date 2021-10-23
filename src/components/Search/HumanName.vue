<template>
  <div class="main-container">
    <div class="component-name">
      <h2>Nom humain</h2>
    </div>
    <div class="gender-container">
      <b-button variant="light">Masculin</b-button>
      <b-button variant="light">Féminin</b-button>
    </div>
    <div class="search-container">
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
    </div>
    <div class="result-container">
      <b-form-input></b-form-input>
    </div>
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
</style>