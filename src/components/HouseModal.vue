<template>
  <div class="row">
    <!-- Modal -->
    <div
      class="modal fade"
      id="create-house-modal"
      tabindex="-1"
      role="dialog"
      aria-labelledby="modelTitleId"
      aria-hidden="true"
    >
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Create House</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body">
            <div class="container-fluid">
              <form @submit.prevent="createCar">
                <div class="form-group row">
                  <label for="levels" class="col-sm-1-12 col-form-label">Levels</label>
                  <div class="col-sm-1-12">
                    <input
                      type="text"
                      class="form-control"
                      name="levels"
                      id="inputName"
                      placeholder="Enter Levels Here...."
                      v-model="newHouse.levels"
                      required
                    />
                  </div>
                </div>
                <div class="form-group row">
                  <label for="bedrooms" class="col-sm-1-12 col-form-label">Bedrooms</label>
                  <div class="col-sm-1-12">
                    <input
                      type="text"
                      class="form-control"
                      name="bedrooms"
                      id="inputName"
                      placeholder="Enter Bedrooms Here...."
                      v-model="newHouse.bedrooms"
                      required
                    />
                  </div>
                </div>
                <div class="form-group row">
                  <label for="bathrooms" class="col-sm-1-12 col-form-label">Bathrooms</label>
                  <div class="col-sm-1-12">
                    <input
                      type="texnumbert"
                      class="form-control"
                      name="bathrooms"
                      id="inputName"
                      placeholder="Enter Bathrooms Here...."
                      v-model="newHouse.bathrooms"
                      required
                    />
                  </div>
                </div>
                <div class="form-group row">
                  <label for="price" class="col-sm-1-12 col-form-label">Price</label>
                  <div class="col-sm-1-12">
                    <input
                      type="number"
                      class="form-control"
                      name="price"
                      id="inputName"
                      placeholder="Enter Price Here...."
                      v-model="newHouse.price"
                      required
                    />
                  </div>
                </div>
                <div class="form-group row">
                  <label for="imgUrl" class="col-sm-1-12 col-form-label">Image Url</label>
                  <div class="col-sm-1-12">
                    <input
                      type="text"
                      class="form-control"
                      name="imgUrl"
                      id="inputName"
                      placeholder="Enter Image Url Here...."
                      v-model="newHouse.imgUrl"
                      required
                    />
                  </div>
                </div>
                <div class="form-group row">
                  <label for="description" class="col-sm-1-12 col-form-label">Description</label>
                  <div class="col-sm-1-12">
                    <input
                      type="text"
                      class="form-control"
                      name="description"
                      id="inputName"
                      placeholder="Enter Description Here...."
                      v-model="newHouse.description"
                    />
                  </div>
                </div>
                <!-- <fieldset class="form-group row">
                  <legend class="col-form-legend col-sm-1-12">Group name</legend>
                  <div class="col-sm-1-12"></div>
                </fieldset>-->
                <div class="form-group row">
                  <div class="offset-sm-2 col-sm-10">
                    <button type="submit" class="btn btn-primary">Make House</button>
                  </div>
                </div>
              </form>
            </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Cancel</button>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- Modal End -->
</template>

<script>
// @ is an alias to /src

export default {
  name: "HouseModal",
  data() {
    return {
      newHouse: {},
    };
  },
  mounted() {},
  computed: {},
  methods: {
    createHouse() {
      this.$store.dispatch("createHouse", this.newHouse);
      this.newHouse = {};
      $("#create-house-modal").modal("hide");
    },
  },
  components: {},
};
</script>