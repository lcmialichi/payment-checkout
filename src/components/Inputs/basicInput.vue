<template>
  <div>
    <v-container class="pt-2 pb-1">
        <label>{{ label }}</label>
    </v-container>
    <v-container class="pt-1">
      <input 
        :id="id"
        class="border-solid"
        :size="size"
        :placeholder="placeHolder"
        :disabled="disabled"
        v-model="value"
        @change="valueChanged"
        >
    </v-container>
  </div>
  </template>
  <style scoped>
  .border-solid {
    border-radius: 4px;
    border-width: 1px;
    border-style: solid;
    border-color: #CED4DA;
    max-width: 100%;
    max-height: 100%;
    height: 40px
  }
  </style>
  <script>
  export default {
    name: 'BasicInput',
    props: {
      id: {
        type: String,
      },
      label: {
        type: String,
        default: ""
      },
      placeHolder: {
        type: String,
        default: ""
      },
      disabled: {
        type: Boolean,
        default: false
      },
      size: {
        type: Number,
        default: 20
      },
    },
    data(){
      return {
        value: ""
      }
    },
    methods:{
      valueChanged ()  {
        this.$emit("value",this.value, this.id)  
      }
    }
  }
  </script>
  