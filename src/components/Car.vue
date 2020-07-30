<template>
  <div class="car col-3 border rounded mb-3" @click="moveToCarPage">
    <h3>{{carData.make}}</h3>
    <h3>{{carData.model}}</h3>
    <img class="img-fluid" :src="carData.imgUrl" alt />
  </div>
</template>



<script>
// @ is an alias to /src

export default {
  name: "car",
  props: ["carData"],
  data() {
    return {};
  },
  computed: {},
  methods: {
    moveToCarPage() {
      this.$router.push({ name: "Car", params: { id: this.carData._id } });
    },
  },
  components: {},
};
</script>