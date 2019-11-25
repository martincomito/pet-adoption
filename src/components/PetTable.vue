<template>
  <div>
    <h1>
      We have a total of
      {{ species === "cats" ? getAllCats.length : getAllDogs.length }}
      {{ species }} for adoption
    </h1>
    <br />
    <b-table striped hover :items="pets">
      <template v-slot:cell(name)="data">
        <router-link :to="`/pets/${species}/${data.index}`">{{
          data.value
        }}</router-link>
      </template>
    </b-table>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  props: {
    species: String,
    pets: Array
  },
  computed: {
    ...mapGetters(["getAllCats", "getAllDogs"])
  }
};
</script>
