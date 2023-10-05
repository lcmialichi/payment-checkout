<template>
  <div :style="style">
    <HeaderProduct 
      name="Nome do produto"
      price="50.00"
      description="Plano mensal com renovação automática"
      contact="contatolivrediet@gmail.com"
    />

    <UserForm
      name
      email
      phone
      cep
      address
      number
      complement
      neighborhood
      city
      state
      @inputs="userFormData"
    />
  </div>
</template>
<style scoped>
</style>

<script>
import HeaderProduct from '@/layouts/HeaderProduct';
import UserForm from '@/layouts/UserForm';

export default {
  name: 'App',
  components: {
    HeaderProduct,
    UserForm,
  },
  data(){
    return {
      style: {
      }
    }
  },
  methods: {
    userFormData(updateValue){
      console.log(updateValue)
    }
  }
};
</script>
