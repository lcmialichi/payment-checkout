<template>
    <v-card
      class="mx-auto my-12"
      max-width="680"
      max-height="250"
    >
      <v-row class="align-center" justify="start">
        <v-col cols="3" class="pa-6">
          <v-img
          class="rounded-image"
          width="120"
          height="150"
          left
          src="@/assets/headerImage.jpg"
          ></v-img>
        </v-col>
        <v-col cols="6">
          <v-card-text>
            <p class="title-style">{{ name }}</p>
            <p class="orange-text">R$ {{ price }} / mês</p>
            <p>{{ description}}</p>
          </v-card-text>
        </v-col>
      </v-row>
      <v-row no-gutters color="#FF6905">
        <v-sheet color="#FF6905" max-height="32" width="680" class="text-xs-center">
          <div class="text-xs-center pa-1 ml-1">
            <p class="white--text">{{ contact }}</p>
          </div>
        </v-sheet>
      </v-row>
    </v-card>
  </template>
  
  <style scoped>
  .rounded-image {
    border-radius: 4px;
  }
  .orange-text{
    color: var(--brand-colors-orange-pay-500, #FF6905); 
    font-family: Inter;
    font-size: 20px;
    font-style: normal;
    font-weight: 600;
    line-height: normal; 
  }
  
  .title-style{
    color: var(--text-colors-grey-pay-500, #303133);
    font-family: Inter;
    font-size: 16px;
    font-style: normal;
    font-weight: 700;
    line-height: normal; 
  }
  
  </style>
  <script>
  export default {
    name: 'HeaderProduct',
    props: {
      name: {
        type: String,
        default: "-"
      },
      price: {
        type: Number,
        default: 0.0
      },
      description:  {
        type: String,
        default: "-"
      },
      contact:  {
        type: String,
        default: "-"
      },
    },
    mounted: () => {

    }
  }
  </script>
  