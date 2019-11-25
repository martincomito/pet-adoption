<template>
  <div>
    <PetTable species="cats" :pets="cats" />
  </div>
</template>

<script>
import PetTable from "@/components/PetTable.vue";
import { mapState, mapGetters } from "vuex";
export default {
  components: {
    PetTable
  },
  data() {
    return {};
  },
  computed: {
    ...mapState(["cats"]),
    ...mapGetters(["getAllCats"])
  }
};
</script>
