<template>
  <v-app>
    <v-main>
      <PaymentMethod />
    </v-main>
  </v-app>
</template>

<script>
import PaymentMethod from './views/PaymentMethod';

export default {
  name: 'App',

  components: {
    PaymentMethod,
  },

  data: () => ({
    //
  }),
};
</script>
