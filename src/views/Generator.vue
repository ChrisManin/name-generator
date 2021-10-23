<template>
  <div class="generator">
    <b-container-fluid>
      <b-row align-h="around">
        <b-col sm="5">
          <HumanName />
        </b-col>
      </b-row>
    </b-container-fluid>
  </div>
</template>

<script>
import HumanName from "../components/Search/HumanName.vue";

export default {
  name: "Generator",
  components: {
    HumanName,
  },
};
</script>