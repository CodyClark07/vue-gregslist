<template>
  <div class="row">
    <!-- Modal -->
    <div
      class="modal fade"
      id="create-car-modal"
      tabindex="-1"
      role="dialog"
      aria-labelledby="modelTitleId"
      aria-hidden="true"
    >
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Create Car</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body">
            <div class="container-fluid">
              <form @submit.prevent="createCar">
                <div class="form-group row">
                  <label for="make" class="col-sm-1-12 col-form-label">Make</label>
                  <div class="col-sm-1-12">
                    <input
                      type="text"
                      class="form-control"
                      name="make"
                      id="inputName"
                      placeholder="Enter Make Here...."
                      v-model="newCar.make"
                      required
                    />
                  </div>
                </div>
                <div class="form-group row">
                  <label for="model" class="col-sm-1-12 col-form-label">Model</label>
                  <div class="col-sm-1-12">
                    <input
                      type="text"
                      class="form-control"
                      name="model"
                      id="inputName"
                      placeholder="Enter Model Here...."
                      v-model="newCar.model"
                      required
                    />
                  </div>
                </div>
                <div class="form-group row">
                  <label for="year" class="col-sm-1-12 col-form-label">Year</label>
                  <div class="col-sm-1-12">
                    <input
                      type="texnumbert"
                      class="form-control"
                      name="year"
                      id="inputName"
                      placeholder="Enter Year Here...."
                      v-model="newCar.year"
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
                      v-model="newCar.price"
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
                      v-model="newCar.imgUrl"
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
                      v-model="newCar.description"
                    />
                  </div>
                </div>
                <!-- <fieldset class="form-group row">
                  <legend class="col-form-legend col-sm-1-12">Group name</legend>
                  <div class="col-sm-1-12"></div>
                </fieldset>-->
                <div class="form-group row">
                  <div class="offset-sm-2 col-sm-10">
                    <button type="submit" class="btn btn-primary">Make Car</button>
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
  name: "CarModal",
  data() {
    return {
      newCar: {},
    };
  },
  mounted() {},
  computed: {},
  methods: {
    createCar() {
      this.$store.dispatch("createCar", this.newCar);
      this.newCar = {};
      $("#create-car-modal").modal("hide");
    },
  },
  components: {},
};
</script>