<template>
  <div class="row">
    <div class="col-md-6">
      <br />
      <table class="table table-bordered">
        <thead>
          <tr>
            <th>Property</th>
            <th>Value</th>
          </tr>
        </thead>

        <tbody>
          <!--Flex Direction-->
          <tr>
            <td>
              <label for="flex-direction">Flex Direction</label>
            </td>
            <td>
              <select class="form-control" id="flex-direction" v-model="flexDirection">
                <option value="row">row</option>
                <option value="row-reverse">row-reverse</option>
                <option value="column">column</option>
                <option value="column-reverse">column-reverse</option>
              </select>
            </td>
          </tr>
          <!--Justify Content-->
          <tr>
            <td>
              <label for="justify-content">Justify Content</label>
            </td>
            <td>
              <select class="form-control" id="justify-content" v-model="justifyContent">
                <option value="flex-start">flex-start</option>
                <option value="flex-end">flex-end</option>
                <option value="center">center</option>
                <option value="space-between">space-between</option>
                <option value="space-around">space-around</option>
                <option value="space-around">space-evenly</option>
              </select>
            </td>
          </tr>
          <!--Align Items-->
          <tr>
            <td>
              <label for="align-items">Align Items</label>
            </td>
            <td>
              <select class="form-control" id="align-items" v-model="alignItems">
                <option>stretch</option>
                <option>center</option>
                <option>flex-start</option>
                <option>flex-end</option>
                <option>baseline</option>
              </select>
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
              <code>
                <p>display: flex;</p>
                <p>flex-direction: {{flexDirection}};</p>
                <p>justify-content: {{justifyContent}};</p>
                <p>align-items: {{alignItems}};</p>
              </code>
            </td>
          </tr>
        </tbody>
      </table>

      <!-- Background Color -->
      <!--label for="box-color">Background Color</label>
      <input class="form-control" id="box-color" type="color" v-model="backgroundColor"-->

      <div></div>
    </div>
    <div class="col-md-6 center">
      <div class="main-box" :style="myStyle">
        <div class="box center">1</div>
        <div class="box center">2</div>
        <div class="box center">3</div>
        <div class="box center">4</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      flexDirection: "row",
      justifyContent: "center",
      alignItems: "center",
    };
  },

  computed: {
    myStyle: function () {
      return {
        width: 400 + "px",
        height: 400 + "px",
        backgroundColor: "pink",
        display: "flex",
        flexDirection: this.flexDirection,
        justifyContent: this.justifyContent,
        alignItems: this.alignItems,
      };
    },
  },
};
</script>

<style scoped>
.box {
  background-color: lightblue;
  margin: 5px;
  padding: 20px;
  font-size: 25px;
  font-weight: 600;
  color: #555;
  border: 1px solid rgb(163, 161, 161);
}
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}
code {
  color: green;
}
</style>