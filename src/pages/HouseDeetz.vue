<template>
  <div class="house-deetz">
    <h3>{{house.levels}}</h3>
    <img class="img-fluid" :src="house.imgUrl" alt />
    <h3>{{house.bedrooms}}</h3>
    <h3>{{house.bathrooms}}</h3>
    <h3>${{house.price}}</h3>
    <p>{{house.description}}</p>
    <button class="btn btn-danger" @click="deleteHouse">Delete</button>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "house-deetz",
  data() {
    return {};
  },
  mounted() {
    this.$store.dispatch("getHouse", this.$route.params.id);
  },
  computed: {
    house() {
      return this.$store.state.activeHouse;
    },
  },
  methods: {
    deleteHouse() {
      this.$store.dispatch("deleteHouse", this.house.id);
    },
  },
  components: {},
};
</script>