<template>
  <div class="wizard-box">
    <h1>Summary</h1>
    <div>Name: {{ info.name }}</div>
    <div>Age: {{ info.age }}</div>
    <div>Where do you live: {{ info.country }}</div>
    <div>Package: {{ info.selectedPackage }}</div>
    <div>Premium: {{ info.premium }}</div>
    <button class="action-button btn-white" @click="next(-1)">Back</button>
    <button class="action-button" @click="next(-2)">Buy</button>
  </div>
</template>

<script>
export default {
  name: "StepTwo",
  props: {
    next: Function,
    info: Object,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.form-fields {
  padding: 15px;
  border: 1px solid #ccc;
  border-radius: 3px;
  margin-bottom: 10px;
  width: 100%;
  box-sizing: border-box;
  font-family: montserrat;
  color: #2c3e50;
  font-size: 13px;
}
</style>
