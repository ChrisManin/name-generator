<template>
  <div class="generator">
    <b-container-fluid>
      <b-row align-h="around">
        <b-col sm="5">
          <HumanName />
        </b-col>
        <b-col sm="5">
          <DogName />
        </b-col>
      </b-row>

      <b-row align-h="around">
        <b-col sm="5">
          <CatName />
        </b-col>
        <b-col sm="5">
          <AlienName />
        </b-col>
      </b-row>

      <b-row align-h="around">
        <b-col sm="5">
          <PirateName />
        </b-col>
        <b-col sm="5">
          <SuperHeroName />
        </b-col>
      </b-row>
    </b-container-fluid>
  </div>
</template>

<script>
import HumanName from "../components/Search/HumanName.vue";
import DogName from "../components/Search/DogName.vue";
import CatName from "../components/Search/CatName.vue";
import AlienName from "../components/Search/AlienName.vue";
import PirateName from "../components/Search/PirateName.vue";
import SuperHeroName from "../components/Search/SuperHeroName.vue";

export default {
  name: "Generator",
  components: {
    HumanName,
    DogName,
    CatName,
    AlienName,
    PirateName,
    SuperHeroName,
  },
};
</script>