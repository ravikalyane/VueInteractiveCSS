<template>
  <div>
    <h1 class="display-4">Serach in Vue</h1>
    <hr />
    <button class="btn btn-sm mb-3" @click="show = !show">Show/Hide</button>
    <transition name="fade">
      <div
        v-if="show"
        class="alert alert-primary"
        role="alert"
      >This is a primary alert—check it out!</div>
    </transition>
    <input v-model="searchText" type="text" class="form-control" placeholder="Serach Fruits" />
    <br />
    <table class="table table-bordered">
      <thead>
        <tr>
          <th>Fruit</th>
          <th>Color</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="fruit in searchFruits" :key="fruit.id">
          <td>{{fruit.name}}</td>
          <td>{{fruit.color}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>


<script>
export default {
  data() {
    return {
      fruits: [
        { name: "apple", color: "red" },
        { name: "mango", color: "yellow" },
        { name: "pineapple", color: "yellow" },
        { name: "grapes", color: "green" },
        { name: "oranges", color: "orange" },
        { name: "pomergranate", color: "red" },
        { name: "banana", color: "yellow" },
      ],
      searchText: "",
      show: true,
    };
  },

  computed: {
    searchFruits() {
      return this.fruits.filter((element) => {
        return element.name.match(this.searchText);
      });
    },
  },
};
</script>

<style>
.fade-enter {
  opacity: 0;
}
.fade-enter-active {
  transition: opacity 1s;
}
.fade-leave {
  /**/
}
.fade-leave-active {
  transition: opacity 1s;
  opacity: 0;
}
</style>