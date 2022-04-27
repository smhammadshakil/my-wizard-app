<template>
  <div class="wizard-box">
    <h1>Tell Us about yourself</h1>
    <div class="form-inputs">
      <label>Name</label>
      <input
        v-model="name"
        class="form-fields"
        type="text"
        name="name"
        placeholder="Name"
      />
      <label>Age</label>
      <input
        v-model="age"
        class="form-fields"
        type="text"
        name="age"
        placeholder="Age"
      />
      <label>Where do you live</label>
      <select v-model="country" id="country" class="form-fields">
        <option value="HKD">Hong Kong</option>
        <option value="USD">USA</option>
        <option value="AUD">Australia</option>
      </select>

      <h2>Package</h2>
      <input
        type="radio"
        id="standard"
        v-model="selectedPackage"
        value="standard"
      /><label class="category-label" for="standard">Standard</label>
      <br />
      <input type="radio" id="safe" v-model="selectedPackage" value="safe" />
      <label class="category-label" for="safe"
        >Safe
        <span
          >(+{{ premium * (packageMap.safe - 1) }} {{ country }}, 50%)</span
        ></label
      >
      <br />
      <input
        type="radio"
        id="super-safe"
        v-model="selectedPackage"
        value="superSafe"
      />
      <label class="category-label" for="super-safe"
        >Super Safe
        <span
          >(+{{ premium * (packageMap.superSafe - 1) }} {{ country }},
          75%)</span
        ></label
      >
      <br />
    </div>
    <h2>
      Your premium is: {{ premium * packageMap[selectedPackage] }}
      {{ premium ? country : null }}
    </h2>
    <button class="action-button btn-white" @click="next(-1)">Back</button>
    <button class="action-button" @click="nextStep" :disabled="disableNext">
      Next
    </button>
  </div>
</template>

<script>
export default {
  name: "StepOne",
  props: {
    next: Function,
    saveInfo: Function,
  },
  data() {
    return {
      name: "",
      age: null,
      country: "HKD",
      selectedPackage: "standard",
      currencyMap: {
        HKD: 100,
        USD: 200,
        AUD: 300,
      },
      packageMap: {
        standard: 1,
        safe: 1.5, //for more 50%
        superSafe: 1.75, //for more 75%
      },
    };
  },
  methods: {
    nextStep() {
      let self = this;
      if (self.age >= 100) {
        self.next(2);
      } else {
        self.next(1);
        self.saveInfo({
          name: self.name,
          age: self.age,
          country: self.country,
          selectedPackage: self.selectedPackage,
          premium: self.premium * self.packageMap[self.selectedPackage],
        });
      }
    },
  },
  computed: {
    premium() {
      let self = this;
      if (self.age > 0) {
        return self.age * 10 * self.currencyMap[self.country];
      }
      return 0;
    },
    disableNext() {
      let self = this;
      return !(self.age && self.age > 0 && self.name);
    },
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
  margin-top: 10px;
}
.form-inputs {
  text-align: left;
}
.category-label {
  font-size: 18px;
}
</style>
