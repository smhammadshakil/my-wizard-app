<template>
  <img class="logo" alt="cmp logo" src="./assets/logo.jpeg" />
  <MultiStep />
</template>

<script>
import MultiStep from "./components/MultiStep.vue";

export default {
  name: "App",
  components: {
    MultiStep,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
.logo {
  width: 150px;
}
.action-button {
  width: 150px;
  background: #27ae60;
  font-weight: bold;
  color: white;
  border: 0 none;
  border-radius: 1px;
  cursor: pointer;
  padding: 10px 5px;
  margin: 10px 5px;
}
.action-button:hover:enabled,
.action-button:focus:enabled {
  box-shadow: 0 0 0 2px white, 0 0 0 3px #27ae60;
}
.btn-white {
  background: white;
  color: #27ae60;
}
.wizard-box {
  margin-top: 10px;
  background: whitesmoke;
  border-radius: 15px;
  padding: 1rem;
  box-shadow: rgba(0, 0, 0, 0.05) 0px 6px 24px 0px,
    rgba(0, 0, 0, 0.08) 0px 0px 0px 1px;
}
</style>
