<template>
  <div>
    <br />
    <div class="row">
      <div class="col-md-6">
        <table class="table table-bordered">
          <thead>
            <tr>
              <td>Property</td>
              <td>Value</td>
            </tr>
          </thead>

          <tbody>
            <tr>
              <td>Color 1</td>
              <td>
                <input type="color" v-model="colorOne" />
              </td>
            </tr>
            <tr>
              <td>Color 2</td>
              <td>
                <input type="color" v-model="colorTwo" />
              </td>
            </tr>
            <tr>
              <td>Linear/Radial</td>
              <td>
                <input type="radio" value="linear" v-model="type" />
                <label for="linear">linear</label>

                <input type="radio" value="radial" v-model="type" />
                <label for="radial">radial</label>
              </td>
            </tr>
            <tr v-if="type == 'linear'">
              <td>Angle</td>
              <td>
                <input type="range" min="-180" max="180" v-model="angle" />
                <span class="pl-3">{{angle}}deg</span>
              </td>
            </tr>
          </tbody>
        </table>

        <!-- CSS Code -->
        <table class="table table-bordered">
          <tbody>
            <tr>
              <td>
                <p>
                  <strong>Code:</strong>
                </p>
                <code>background-image: linear-gradient({{angle}}deg,{{colorOne}}, {{colorTwo}})</code>
              </td>
            </tr>
          </tbody>
        </table>
      </div>

      <div class="col-md-6">
        <div class="box" :style="myStyle"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      colorOne: "#D9AFD9",
      colorTwo: "#97D9E1",
      angle: 0,
      type: "radial",
    };
  },

  computed: {
    myStyle: function () {
      return {
        backgroundImage:
          this.type == "linear"
            ? this.type +
              "-gradient(" +
              this.angle +
              "deg," +
              this.colorOne +
              "," +
              this.colorTwo +
              ")"
            : this.type +
              "-gradient(" +
              this.colorOne +
              "," +
              this.colorTwo +
              ")",
        width: 600 + "px",
        height: 400 + "px",
      };
    },
  },
};
</script>scrip

<style scoped>
.box {
  width: 600px;
  height: 400px;
  background-color: black;
}
table {
  table-layout: fixed;
}
</style>