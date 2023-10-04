<template>
  <div>
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
      cep,
      address
    />
  </div>
</template>

<script>
import HeaderProduct from '@/components/cards/HeaderProduct';
import UserForm from '@/components/cards/UserForm';

export default {
  name: 'App',

  components: {
    HeaderProduct,
    UserForm,
  },

  data: () => ({
    //
  }),
};
</script>
