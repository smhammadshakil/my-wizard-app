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
