<template>
<div id="app">
    <div class="wrapper">
        <header>Me Personal Costs</header>
      <main>
        <button @click="addFormRender = !addFormRender">ADD NEW COSTS</button>
        <add-payment-form v-show="addFormRender" :render="addFormRender" @addNewPayment="onDataPaymentAdd" @render="addFormRender=false"/>
        <payments-display :items="paymentsList"/>
      </main>
    </div>
</div>
</template>

<script>
import PaymentsDisplay from "./components/PaymentsDisplay";
import AddPaymentForm from "@/components/AddPaymentForm";

export default {
  name: 'App',
  components: {
    PaymentsDisplay,
    AddPaymentForm,

  },
  data(){
    return {
      paymentsList: [],
      addFormRender: false,
    }
  },
  methods: {
    fetchData () {
      return [
        {
          date: '28.03.2020',
          category: 'Food',
          value: 169,
        },
        {
          date: '24.03.2020',
          category: 'Transport',
          value: 360,
        },
        {
          date: '24.03.2020',
          category: 'Food',
          value: 532,
        },
      ]
    },
    onDataPaymentAdd(data){
      this.paymentsList.push(data)
    }
    },
  created() {
    this.paymentsList = this.fetchData()
  }
}
</script>

<style lang="scss">

</style>
