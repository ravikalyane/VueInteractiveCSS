<template>
  <div>
    <ul class="navbar">
      <li>
        <button class="btn btn-sm btn-success" @click="selectedComponent = 'vueResource'">VueResource</button>
      </li>
      <li>
        <button class="btn btn-sm btn-success" @click="selectedComponent = 'practice'">Practice</button>
      </li>
      <li>
        <button class="btn btn-sm btn-primary" @click="selectedComponent = 'flexbox'">Flexbox</button>
      </li>
      <li>
        <button class="btn btn-sm btn-secondary" @click="selectedComponent = 'border'">Border</button>
      </li>
      <li>
        <button
          class="btn btn-sm btn-warning"
          @click="selectedComponent = 'background'"
        >Background</button>
      </li>
    </ul>
    <div class="container">
      <keep-alive>
        <component :is="selectedComponent"></component>
      </keep-alive>
    </div>
  </div>
</template>

<script>
import Border from "./components/Border";
import Flexbox from "./components/Flexbox";
import Background from "./components/Background";
import Practice from "./components/Practice";
import VueResource from "./components/VueResource";
export default {
  data: function () {
    return {
      selectedComponent: "flexbox",
    };
  },
  components: {
    border: Border,
    flexbox: Flexbox,
    background: Background,
    practice: Practice,
    vueResource: VueResource
  },
};
</script>

<style scoped>
.navbar {
  height: 10vh;
  list-style: none;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: aquamarine;
}
.btn {
  margin: auto 10px;
}

button, button:focus {
  box-shadow: none !important;
  border-radius: 0%!important;
}

@media only screen and (max-width: 768px)  {
  .navbar{
    display: none;
  }
}
</style>
