<template>
<div id="app">
    <div class="wrapper">
        <header>Me Personal Costs</header>
      <main>
      <payments-display :items="paymentsList"/>
      </main>
    </div>
</div>
</template>

<script>
import PaymentsDisplay from "./components/PaymentsDisplay";

export default {
  name: 'App',
  components: {
    PaymentsDisplay,

  },
  data(){
    return {
      paymentsList: [],

    }
  },
  methods: {

  }
}
</script>

<style lang="scss">

</style>
