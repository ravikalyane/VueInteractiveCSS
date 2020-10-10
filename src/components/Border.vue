<template>
  <div>
    <br />
    <div class="row">
      <div class="col-md-6">
        <table class="table table-bordered">
          <thead>
            <th>Property</th>
            <th>Value</th>
          </thead>
          <tbody>
            <!-- Width -->
            <tr>
              <td>Width</td>
              <td class="center-align">
                <input type="range" min="1" max="20" v-model="borderWidth" />
                <span class="pl-3">{{borderWidth}}px</span>
              </td>
            </tr>
            <!-- Style -->
            <tr>
              <td>Style</td>
              <td>
                <select class="form-control" id="border-style" v-model="borderStyle">
                  <option value="solid">solid</option>
                  <option value="dotted">dotted</option>
                  <option value="dashed">dashed</option>
                  <option value="double">double</option>
                  <option value="groove">groove</option>
                  <option value="ridge">ridge</option>
                </select>
              </td>
            </tr>
            <!-- Radius -->
            <tr>
              <td>Radius</td>
              <td>
                <input type="range" min="0" max="50" v-model="borderRadius" />
                <span class="pl-3">{{borderRadius}}%</span>
              </td>
            </tr>
            <!-- Color -->
            <tr>
              <td>Color</td>
              <td>
                <input type="color" id="color-input" value="#FFC0CB" v-model="borderColor" />
                <span class="pl-3">{{borderColor}}</span>
              </td>
            </tr>
          </tbody>
        </table>

        <table class="table table-bordered">
          <tbody>
            <tr>
              <td>
                <p>
                  <strong>Code:</strong>
                </p>
                <p>
                  <code>border: {{borderWidth}}px {{borderStyle}} {{borderColor}}</code>
                </p>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
      <div class="col-md-6 center">
        <div :style="myStyle">Content</div>
        <br />
        <table class="fixed">
          <tbody>
            <tr>
              <td>
                Width:
                <input type="range" min="200" max="400" v-model="width" />
                {{width}} px
              </td>
            </tr>
            <tr>
              <td>
                Height:
                <input type="range" min="200" max="400" v-model="height" />
                {{height}} px
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      borderWidth: "2",
      borderStyle: "solid",
      borderColor: "#FFC0CB",
      borderRadius: 0,
      width: 400,
      height: 300,
    };
  },

  computed: {
    myStyle: function () {
      return {
        borderWidth: this.borderWidth + "px",
        borderStyle: this.borderStyle,
        borderColor: this.borderColor,
        borderRadius: this.borderRadius + "%",
        width: this.width + "px",
        height: this.height + "px",
        display: "flex",
        justifyContent: "center",
        alignItems: "center",
        fontSize: 50 + "px",
      };
    },
  },
};
</script>

<style scoped>
.border {
  width: 400px;
  height: 300px;
}

.center {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: #555;
}

#color-input {
  padding: 0px;
  height: 30px;
  width: 100px;
}
code {
  color: green;
}
.fixed{
 position: absolute;
 bottom: -20%;
 /*right: 0%;*/
}

.col-md-6{
  height: 450px;
}
</style>