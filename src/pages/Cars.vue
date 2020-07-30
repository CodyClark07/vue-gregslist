<template>
  <div class="cars row">
    <!-- Button trigger modal -->
    <button
      type="button"
      class="col-12 mb-3 btn btn-primary btn-lg"
      data-toggle="modal"
      data-target="#create-car-modal"
    >Post Car</button>
    <CarModal></CarModal>

    <car v-for="car in cars" :carData="car" :key="car.id" />
  </div>
</template>



<script>
// @ is an alias to /src
import Car from "../components/Car";
import CarModal from "../components/CarModal";

export default {
  name: "Cars",
  data() {
    return {};
  },
  mounted() {
    this.$store.dispatch("getCars");
  },
  computed: {
    cars() {
      return this.$store.state.cars;
    },
  },
  methods: {},
  components: {
    Car,
    CarModal,
  },
};
</script>