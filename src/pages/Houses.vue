<template>
  <div class="houses row">
    <!-- Button trigger modal -->
    <button
      type="button"
      class="col-12 mb-3 btn btn-primary btn-lg"
      data-toggle="modal"
      data-target="#create-house-modal"
    >Post House</button>
    <HouseModal></HouseModal>

    <house v-for="house in houses" :houseData="house" :key="house.id" />
  </div>
</template>


<script>
import House from "../components/House";
import HouseModal from "../components/HouseModal";

export default {
  name: "Houses",
  data() {
    return {};
  },
  mounted() {
    this.$store.dispatch("getHouses");
  },
  computed: {
    houses() {
      return this.$store.state.houses;
    },
  },
  methods: {},
  components: {
    House,
    HouseModal,
  },
};
</script>


<style scoped>
</style>