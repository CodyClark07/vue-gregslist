<template>
  <div class="house col-3 border rounded mb-3" @click="moveToHousePage">
    <h3>${{houseData.price}}</h3>

    <img class="img-fluid" :src="houseData.imgUrl" alt />
  </div>
</template>


<script>
export default {
  name: "house",
  props: ["houseData"],
  data() {
    return {};
  },
  computed: {},
  methods: {
    moveToHousePage() {
      this.$router.push({ name: "House", params: { id: this.houseData._id } });
    },
  },
  components: {},
};
</script>


<style scoped>
</style>