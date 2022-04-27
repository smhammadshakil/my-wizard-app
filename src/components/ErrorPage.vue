<template>
  <div class="wizard-box">
    <h1>Ooops</h1>
    <h4>
      Your age is over our accepted limit. <br />We are sorry we can not insure
      you now
    </h4>
    <button class="action-button" @click="next(-3)">Ok :(</button>
  </div>
</template>

<script>
export default {
  name: "ErrorPage",
  props: {
    next: Function,
  },
};
</script>
