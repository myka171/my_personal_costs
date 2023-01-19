<template>
 <div class="payment-content">
      <input placeholder="Category" v-model="category">
      <input placeholder="Date" v-model="date">
      <input placeholder="Value" v-model="value">
      <button @click="onSaveClick">Save</button>
 </div>
</template>

<script>
export default {
  name: "AddPaymentForm",
  props: {
    addFormRender: {
      type: Boolean,
      default: true,
    }
  },
    data(){
      return {
          category: '',
          date: '',
          value: 0,
      }
    },
  computed:{
    getCurrentDate(){
      const today = new Date();
      const day = today.getDate();
      const month = today.getMonth() + 1;
      const year = today.getFullYear();
      return `${day}.${month}.${year}`
    }
  },
  methods: {
    onSaveClick(){
      const data = {
        value: this.value,
        category: this.category,
        date: this.date || this.getCurrentDate,

      }
      this.$emit('addNewPayment', data)
      this.$emit('render')
    }
  }
}

</script>

<style >

</style>